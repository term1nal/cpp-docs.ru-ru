---
title: Srwlockexclusivetraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7737c802634b618b9ea363c231a44d9381ad30ae
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235169"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits - структура

Описывает общие характеристики `SRWLock` класс в режиме эксклюзивной блокировки.

## <a name="syntax"></a>Синтаксис

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | --------------------------------------------------------------------------
`Type` | Синоним для указателя на [SRWLOCK](../windows/srwlock-class.md) класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                        | Описание
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits::GetInvalidValue](#getinvalidvalue) | Извлекает `SRWLockExclusiveTraits` объект, который всегда является недопустимым.
[SRWLockExclusiveTraits::Unlock](#unlock)                   | Освобождает управлением указанного `SRWLock` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>SRWLockExclusiveTraits::GetInvalidValue

Извлекает `SRWLockExclusiveTraits` объект, который всегда является недопустимым.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Пустой объект `SRWLockExclusiveTraits`

## <a name="unlock"></a>SRWLockExclusiveTraits::Unlock

Освобождает управлением указанного `SRWLock` объекта.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Параметры

*SRWLOCK*<br/>
Дескриптор `SRWLock` объекта.
