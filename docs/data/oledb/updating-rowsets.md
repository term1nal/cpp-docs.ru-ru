---
title: Обновление наборов строк | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: be82fb1c1f77ae3204bed54257062f362d286844
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083831"
---
# <a name="updating-rowsets"></a>обновление наборов строк

Обновление или запись данных в хранилище данных — одна из простейших операций баз данных. В OLE DB используется простой механизм обновления: приложение-клиент задает значения привязанных членов данных, а затем записывает эти значения в набор строк; затем клиент запрашивает у поставщика обновление хранилища данных.  
  
Клиенты могут выполнять следующие типы обновлений в данных набора строк: задание значений столбцов в строке, вставка строки и удаление строки. Чтобы можно было использовать эти операции, класс шаблона OLE DB [CRowset](../../data/oledb/crowset-class.md) реализует интерфейс [IRowsetChange](/previous-versions/windows/desktop/ms715790) и переопределяет следующие методы интерфейса:  
  
- Команда[SetData](../../data/oledb/crowset-setdata.md) изменяет значения столбцов в строке набора строк; она эквивалентна команде SQL UPDATE.  
  
- Команда[Insert](../../data/oledb/crowset-insert.md) вставляет строку в набор строк; она эквивалентна команде SQL INSERT.  
  
- Команда[Delete](../../data/oledb/crowset-delete.md) удаляет строки из набора строк; она эквивалентна команде SQL DELETE.  
  
## <a name="supporting-update-operations"></a>Поддержка операций обновления  

При создании клиента с помощью мастера клиента ATL OLE DB вы можете поддержать операции обновления, установив флажки **Изменить**, **Вставить**и **Удалить**. При их установке мастер изменяет код соответствующим образом, чтобы поддержать выбранные типы изменений. Однако если вы не используете мастер, вам потребуется задать следующие свойства набора строк для `VARIANT_TRUE` , чтобы поддержать обновления:  
  
- `DBPROPVAL_UP_CHANGE` позволяет изменять значения данных в строке.  
  
- `DBPROPVAL_UP_INSERT` позволяет вставить строку.  
  
- `DBPROPVAL_UP_DELETE` позволяет удалить строку.  
  
Свойства задаются следующим образом.  
  
```cpp  
CDBPropSet ps(DBPROPSET_ROWSET);  

ps.AddProperty(DBPROP_IRowsetChange, true)  
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
```  
  
Операции изменения, вставки или удаления могут привести к сбою, если какие-то из столбцов не поддерживают запись. Измените схему курсоров, чтобы исправить это.  
  
## <a name="setting-data-in-rows"></a>Задание данных в строках  

[CRowset::SetData](../../data/oledb/crowset-setdata.md) задает значения данных в одном или нескольких столбцах текущей строки. Следующий код задает значения членов данных, привязанные к столбцам Name и Units in Stock таблицы Products, а затем вызывает `SetData` , чтобы записать эти значения в сотую строку набора строк:  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Candle" ) );  

product.m_UnitsInStock = 10000;  
  
// Set the data  
HRESULT hr = product.SetData();  
```  
  
## <a name="inserting-rows-into-rowsets"></a>Вставка строк в наборы строк  

[CRowset::Insert](../../data/oledb/crowset-insert.md) создает и инициализирует новую строку, используя данные из метода доступа. `Insert` Создает новую строку после текущей строки; необходимо указать, следует ли увеличить текущей строки на следующую строку или оставить его без изменений. Это можно сделать, задав параметр *bGetRow* :  
  
```cpp  
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)  
```  
  
- **false** (значение по умолчанию) указывает, что указатель текущей строки переводится на следующую строку (в этом случае он будет указывать на вставленную строку);  
  
- **true** указывает, что текущая строка остается в том же положении.  
  
Следующий код задает значения членов данных, привязанные к столбцам таблицы Products, а затем вызывает `Insert` Чтобы вставить новую строку с этими значениями после сотой строки набора строк. Рекомендуется задать все значения столбцов, чтобы избежать появления неопределенных данных в новой строке:  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Set the column values for a row of the Product table, then insert the row  
product.m_ProductID = 101;  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Candle" ) );  

product.m_SupplierID = 27857;  
product.m_CategoryID = 372;  
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit,  
           _T( "Pack of 10" ) );  

product.m_UnitPrice = 20;  
product.m_UnitsInStock = 10000;  
product.m_UnitsOnOrder = 5201;  
product.m_ReorderLevel = 5000;  
product.m_Discontinued = false;  
  
// You must also initialize the status and length fields before setting/inserting data  
// Set the column status values  
m_dwProductIDStatus = DBSTATUS_S_OK;  
m_dwProductNameStatus = DBSTATUS_S_OK;  
m_dwSupplierIDStatus = DBSTATUS_S_OK;  
m_dwCategoryIDStatus = DBSTATUS_S_OK;  
m_dwQuantityPerUnitStatus = DBSTATUS_S_OK;  
m_dwUnitPriceStatus = DBSTATUS_S_OK;  
m_dwUnitsInStockStatus = DBSTATUS_S_OK;  
m_dwUnitsOnOrderStatus = DBSTATUS_S_OK;  
m_dwReorderLevelStatus = DBSTATUS_S_OK;  
m_dwDiscontinuedStatus = DBSTATUS_S_OK;  
  
// Set the column length value for column data members that are not fixed-length types.  
// The value should be the length of the string that you are setting.  
m_dwProductNameLength = 6;             // "Candle" has 6 characters  
m_dwQuantityPerUnitLength = 10;        // "Pack of 10" has 10 characters  
  
// Insert the data  
HRESULT hr = product.Insert();  
```  
  
Более подробный пример см. в описании [CRowset::Insert](../../data/oledb/crowset-insert.md).  
  
Дополнительные сведения о задании членов данных состояния и длины см. в разделе [Члены данных состояния поля в методах доступа, созданных мастером](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
## <a name="deleting-rows-from-rowsets"></a>Удаление строк из наборов строк  

[CRowset::Delete](../../data/oledb/crowset-delete.md) удаляет текущую строку из набора строк. Следующий код вызывает `Delete` для удаления сотой строки набора строк:  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Delete the row  
HRESULT hr = product.Delete();  
```  
  
## <a name="immediate-and-deferred-updates"></a>Немедленные и отложенные обновления  

Если не указано обратное, вызовы `SetData`, `Insert`, и `Delete` методы обновляют хранилище данных немедленно. Вы можете отложить обновления, чтобы клиент сохранил все изменения в локальном кэше, а затем переместил их в хранилище данных при вызове одного из следующих методов обновления.  
  
- [CRowset::Update](../../data/oledb/crowset-update.md) перемещает все ожидающие изменения, внесенные в текущую строку с момента последней выборки или `Update` вызвать на нем.  
  
- [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md) перемещает все ожидающие изменения, внесенные во все строки с момента последней выборки или `Update` вызвать на нем.  
  
Обратите внимание, что обновление в контексте методов обновления относится только к внесению изменений по команде и не должно смешиваться с командой SQL UPDATE (`SetData` эквивалентна команде SQL UPDATE).  
  
Отложенные обновления нужны, например, в случаях выполнения серии банковских транзакций; если одна транзакция будет отменена, вы можете отменить изменение, так как вы не отправляете эту серию изменений, пока последнее из них не будет зафиксировано. Также поставщик может объединить изменения в один вызов по сети, что более эффективно.  
  
Для поддержки отложенных изменений, необходимо задать `DBPROP_IRowsetChange` свойства, а также свойства, описанные в «Поддержка операций обновления»:  
  
```cpp  
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);  
```  
  
При вызове `Update` или `UpdateAll`, методы перемещают изменения из локального кэша в хранилище данных, а затем очищают локальный кэш. Так как обновление перемещает изменения только для текущей строки, важно, чтобы приложение отслеживало, какие строки следует обновлять и когда. В следующем примере показано, как обновить две последовательные строки.  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Wick" ) );  

product.m_UnitsInStock = 10000;  

HRESULT hr = product.SetData();  // No changes made to row 100 yet  
product.Update();                 // Update row 100 now  
  
// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table  
product.MoveNext();  

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName  
           _T( "Wax" ) );  

product.m_UnitsInStock = 500;  

HRESULT hr = product.SetData();  // No changes made to row 101 yet  
product.Update();                 // Update row 101 now  
```  
  
Чтобы гарантировать, что ожидающие изменения перемещены, следует вызвать `Update` перед перемещением в другую строку. Однако если это неэффективно, например когда приложению требуется обновлять сотни строк, вы можете использовать `UpdateAll` для одновременного обновления всех строк.  
  
Например если первый `Update` вызов отсутствовал приведенный выше код, строка 100 осталась бы без изменений, тогда как строка 101 будет изменена. После этого приложение потребовалось бы вызвать `UpdateAll` или вернуться к строке 100 и вызвать `Update` для обновления этой строки.  
  
Наконец, основная причина откладывания изменений, — возможность отменить их. Вызов [CRowset::Undo](../../data/oledb/crowset-undo.md) откатывает состояние локального кэша изменений до состояния хранилища данных перед внесением ожидающих изменений. Важно отметить, что `Undo` не откатывает состояние локального кэша на один шаг (до состояния перед последним изменением); вместо этого она очищает локальный кэш для этой строки. Кроме того `Undo` затрагивает только текущую строку.  
  
## <a name="see-also"></a>См. также  

[Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[Класс CRowset](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790)