---
title: Класс unsupported_feature | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
dev_langs:
- C++
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ed33df07ed6fe9f99f5e9a135e3286672e7a013
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393572"
---
# <a name="unsupportedfeature-class"></a>Класс unsupported_feature

Исключение, возникающее, когда используется неподдерживаемое свойство.

## <a name="syntax"></a>Синтаксис

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[unsupported_feature конструктор](#ctor)|Создает новый экземпляр класса `unsupported_feature` исключение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature__ctor"></a> unsupported_feature

  Создает новый экземпляр исключения unsupported_feature.

### <a name="syntax"></a>Синтаксис

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описание ошибки.

### <a name="return-value"></a>Возвращаемое значение

Объект `unsupported_feature`.

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен** : Concurrency

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
