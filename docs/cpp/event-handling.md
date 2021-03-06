---
title: Обработка событий | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 666fb58168dd0be4ddb011de7c2ee0fc4f4e77e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066572"
---
# <a name="event-handling"></a>Обработка событий

Обработка событий в основном поддерживается для COM-классов (классов C++, реализующих COM-объектов, обычно с помощью классов ATL или [coclass](../windows/coclass.md) атрибут).  Дополнительные сведения см. в разделе [обработка событий в COM](../cpp/event-handling-in-com.md).

Обработка событий также поддерживается для собственных классов C++ (классов C++, которые не реализуют объекты COM-модели), однако эта поддержка является устаревшей и в будущих выпусках будет удалена.  Дополнительные сведения см. в разделе [обработка событий в неуправляемом коде C++](../cpp/event-handling-in-native-cpp.md).

Обработка событий поддерживает одно- и многопоточное использование и защищает данные от одновременного многопоточного доступа. Она также позволяет извлекать вложенные классы из источника события или классов приемника и поддерживать расширенный поиск и получение событий в производном классе.

Visual C++ включает атрибуты и ключевые слова для объявления событий и обработчиков событий. Атрибуты событий и ключевые слова можно использовать в программах CLR и собственных программах С++.

|Раздел|Описание|
|-----------|-----------------|
|[event_source](../windows/event-source.md)|Создает источник событий.|
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий (получатель).|
|[__event](../cpp/event.md)|Объявление события.|
|[__raise](../cpp/raise.md)|Выделяет место вызова события.|
|[__hook](../cpp/hook.md)|Связывает метод обработчика с событием.|
|[__unhook](../cpp/unhook.md)|Отменяет связь метода обработчика с событием.|

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)