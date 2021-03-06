---
title: Элементы списков и списки изображений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86395798a91852860b20f40f3ee0a53c745816c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440593"
---
# <a name="list-items-and-image-lists"></a>Элементы списков и списки изображений

«Элемент» в элементе управления списком ([CListCtrl](../mfc/reference/clistctrl-class.md)) состоит из значка, метку и, возможно, другие сведения (в «подэлементы»).

Значки для элементов управления списка, содержащихся в списках изображений. Один список изображений содержит полноразмерное значков, используемых в представлении значков. Список второй, необязательный, образ содержит уменьшенных версий для использования в других представлениях элемента управления и те же значки. Третий необязательный список содержит «состояние» образов, например, флажки для отображения перед мелкие значки в определенных режимах. Четвертый необязательный список содержит изображений, отображаемых в элементах отдельного заголовка элемента управления списком.

> [!NOTE]
>  Если элемент управления списка создается со стилем LVS_SHAREIMAGELISTS, вы несете ответственность по уничтожению списков изображений, когда они больше не используются. Укажите этот стиль, если назначить тот же образ списки для нескольких элементов управления представления списком; в противном случае более одного элемента управления может попытаться уничтожить один список изображений.

Дополнительные сведения о списке элементов, см. в разделе [списки изображений представление списка](/windows/desktop/Controls/using-list-view-controls) и [элементами и подэлементами](/windows/desktop/Controls/using-list-view-controls) в пакете Windows SDK. Также см. в разделе класса [CImageList](../mfc/reference/cimagelist-class.md) в *Справочник по библиотеке MFC* и [использование CImageList](../mfc/using-cimagelist.md) в этот сборник статей.

Чтобы создать элемент управления списка, необходимо предоставить списков изображений для использования при вставке новых элементов в списке. В следующем примере демонстрируется Эта процедура, где *m_pImagelist* — это указатель типа `CImageList` и *m_listctrl* является `CListCtrl` элемент данных.

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

Тем не менее если вы не планируете отображение значков в представлении списка или управления "список", нет необходимости списков изображений.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

