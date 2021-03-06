---
title: 'Практическое: обновление объектов интерфейса пользователя | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8afe8f6f7594c2dff75125aa56a210505bf5301d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410592"
---
# <a name="how-to-update-user-interface-objects"></a>Практическое руководство. Обновление объектов интерфейса пользователя

Как правило элементы меню и кнопки панели инструментов имеют несколько состояний. Например элемент меню отображается серым цветом (серым цветом) в случае недоступности в контексте присутствует. Пункты меню также может быть установлен или снят. Также можно отключить кнопку панели инструментов, если она недоступна, или можно проверить.

Тех, кто обновляет состояние этих элементов, как программировать изменились условия логически, в том случае, если элемент меню создает команду, которая обрабатывается, например, документ, имеет смысл иметь обновить элемент меню документа. Возможно, документ содержит сведения, на котором основан обновления.

Если команда имеет несколько объектов пользовательского интерфейса (возможно пункта меню и кнопки панели инструментов), оба направляются в одну и ту же функцию обработчика. Это инкапсулирует код обновления пользовательского интерфейса для всех объектов эквивалентные пользовательского интерфейса в одном месте.

Платформа предоставляет удобный интерфейс для автоматического обновления объектов пользовательского интерфейса. Вы можете заниматься другими способами, но интерфейс, предоставленный эффективный и простой в использовании.

В следующих разделах описывается использование обработчиков обновления:

- [Ситуации вызова обработчиков обновления](../mfc/when-update-handlers-are-called.md)

- [Макрос ON_UPDATE_COMMAND_UI](../mfc/on-update-command-ui-macro.md)

- [Класс CCmdUI](../mfc/the-ccmdui-class.md)

## <a name="see-also"></a>См. также

[Меню](../mfc/menus-mfc.md)

