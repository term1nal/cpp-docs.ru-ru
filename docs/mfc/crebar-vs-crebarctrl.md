---
title: CReBar или CReBarCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6133e298cd0bc5b497fbbba47982a755afeefb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442855"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar или CReBarCtrl

MFC предоставляет два класса для создания rebars: [CReBar](../mfc/reference/crebar-class.md) и [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (который создает оболочку для общего элемента управления Windows API). `CReBar` предоставляет все функциональные возможности стандартного элемента главной панели управления и автоматически обрабатывает многие необходимые общие параметры управления и структуры.

`CReBarCtrl` Представляет класс-оболочку для элемента управления "Главная панель" Win32 и таким образом, может быть проще реализовать, если вы не планируете интегрировать в архитектуру MFC главной панели. Если вы планируете использовать `CReBarCtrl` и интегрировать в архитектуру MFC главной панели, необходимо выполнить дополнительные действия для обмена данными операции управления "Главная панель" для MFC. Это взаимодействие несложно; Тем не менее, это дополнительную работу, ненужные при использовании `CReBar`.

Visual C++ предоставляет два способа для использования стандартного элемента управления "Главная панель".

- Создайте "Главная панель" с помощью `CReBar`, а затем вызвать [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) для получения доступа к `CReBarCtrl` функций-членов.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` — встраиваемая функция члена, к которому приводятся **это** указатель объекта главной панели. Это означает, что, во время выполнения, вызов функции содержит отсутствие накладных расходов на.

- Создайте контейнер с помощью [CReBarCtrl](../mfc/reference/crebarctrl-class.md)в конструктор.

Каждый из этих методов будет предоставить вам доступ к функции-члены элемента управления "Главная панель". При вызове `CReBar::GetReBarCtrl`, он возвращает ссылку на `CReBarCtrl` объекта, поэтому вы можете использовать любой набор функций-членов. См. в разделе [CReBar](../mfc/reference/crebar-class.md) сведения о построении и создания "Главная панель" с помощью `CReBar`.

## <a name="see-also"></a>См. также

[Использование CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

