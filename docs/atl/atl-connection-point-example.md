---
title: Пример точки подключения ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9aafd2676b1816737015b6af4fdbc9b3a710ae5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752362"
---
# <a name="atl-connection-point-example"></a>Пример точки подключения ATL

В этом примере показан объект, который поддерживает [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) как исходящий интерфейс:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

При указании `IPropertyNotifySink` как исходящий интерфейс, можно использовать класс [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) вместо `IConnectionPointImpl`. Пример:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>См. также

[Точка подключения](../atl/atl-connection-points.md)

