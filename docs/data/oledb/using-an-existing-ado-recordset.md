---
title: Использование существующего набора записей ADO | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d3a0b2d2da67e4db55dbf3a3f5b23c0c88797dd7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065352"
---
# <a name="using-an-existing-ado-recordset"></a>Использование существующего набора записей ADO

Создайте шаблоны потребителей OLE DB и Active Data Objects (ADO), открыть набор записей (соответствующий набор строк в шаблоны потребителей OLE DB) с помощью ADO. Если у вас есть набор записей, выполните следующие действия для подключения к набор строк OLE DB.  
  
1. Вызовите `QueryInterface` для `IRowset` и `IAccessor` указатели.  
  
    ```cpp  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk* указывает `IUnknown` объекта набора записей ADO.  
  
1. Назначить их соответствующие классы шаблонов потребителей OLE DB для доступа и строк.  
  
    ```cpp  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## <a name="see-also"></a>См. также  

[Использование методов доступа](../../data/oledb/using-accessors.md)