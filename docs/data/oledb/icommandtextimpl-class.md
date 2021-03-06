---
title: Класс ICommandTextImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b73111fe05a7c752edda0c95f1289a125828d4a5
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082557"
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl

Предоставляет реализацию для [ICommandText](/previous-versions/windows/desktop/ms714914) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
### <a name="parameters"></a>Параметры  

*T*<br/>
Команда класс, производный от `ICommandTextImpl`. 

## <a name="requirements"></a>Требования  

**Заголовок:** altdb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetCommandText](#getcommandtext)|Возвращает набор при последнем вызове для текста команд [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|  
|[SetCommandText](#setcommandtext)|Задает текст команды, заменив существующий текст команды.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_strCommandText](#strcommandtext)|Сохраняет текст команды.|  
  
## <a name="remarks"></a>Примечания  

Обязательный интерфейс на команды.  
 
## <a name="getcommandtext"></a> ICommandTextImpl::GetCommandText

Возвращает набор при последнем вызове для текста команд [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect,   
   LPOLESTR * ppwszCommand);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825) в *справочнике программиста OLE DB*. *PguidDialect* параметр игнорируется методом по умолчанию.  

## <a name="setcommandtext"></a> ICommandTextImpl::SetCommandText

Задает текст команды, заменив существующий текст команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,   
   LPCOLESTR pwszCommand);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757) в *справочнике программиста OLE DB*. 

## <a name="strcommandtext"></a> ICommandTextImpl::m_strCommandText

Хранит строку текста команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CComBSTR m_strCommandText;  
```  
  
## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)