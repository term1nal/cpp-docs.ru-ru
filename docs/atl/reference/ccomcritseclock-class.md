---
title: Класс CComCritSecLock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab3c4b349b64b96b8aeb7a53d6bf8809f41cea7b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097787"
---
# <a name="ccomcritseclock-class"></a>Класс CComCritSecLock

Этот класс предоставляет методы для блокировки и разблокировки объект критической секции.

## <a name="syntax"></a>Синтаксис

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Параметры

*TLock*<br/>
Объект для блокировки и разблокировать.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|Конструктор.|
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCritSecLock::Lock](#lock)|Вызовите этот метод, чтобы заблокировать объект критической секции.|
|[CComCritSecLock::Unlock](#unlock)|Вызовите этот метод, чтобы разблокировать объект критической секции.|

## <a name="remarks"></a>Примечания

Этот класс используется для блокирования и разблокирования объектов более безопасным способом, чем с [класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) или [класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock

Конструктор.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Объект критической секции.

*bInitialLock*<br/>
Состояние начального блокировки: **true** означает, что заблокирована.

### <a name="remarks"></a>Примечания

Инициализирует объект критической секции.

##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock

Деструктор

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Примечания

Разблокирует объект критической секции.

##  <a name="lock"></a>  CComCritSecLock::Lock

Вызовите этот метод, чтобы заблокировать объект критической секции.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK, если объект успешно заблокирован или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Если объект уже заблокирован, в отладочных сборках возникнет ошибка УТВЕРЖДЕНИЯ.

##  <a name="unlock"></a>  CComCritSecLock::Unlock

Вызовите этот метод, чтобы разблокировать объект критической секции.

```
void Unlock() throw();
```

### <a name="remarks"></a>Примечания

Если объект уже разблокирован, в отладочных сборках возникнет ошибка УТВЕРЖДЕНИЯ.

## <a name="see-also"></a>См. также

[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)
