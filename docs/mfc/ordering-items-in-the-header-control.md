---
title: Сортировка элементов в элементе управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f446eb557fab4f4ff6396042e832e4584546bd96
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416829"
---
# <a name="ordering-items-in-the-header-control"></a>Сортировка элементов в элементе управления "Заголовок"

Когда вы закончите [добавлении элементов в элемент управления заголовка](../mfc/adding-items-to-the-header-control.md), можно управлять и получать сведения о их порядок со следующими функциями:

- [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) и [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

     Получает и задает порядок элементов заголовка слева направо.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

     Получает значение индекса для определенного заголовка элемента.

В дополнение к предыдущей функции-члены hds_dragdrop-стиль позволяет пользователю перетаскивать элементы заголовка в элементе управления заголовка. Дополнительные сведения см. в разделе [Предоставление поддержки перетаскивания и вставки для элементов заголовка](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)

