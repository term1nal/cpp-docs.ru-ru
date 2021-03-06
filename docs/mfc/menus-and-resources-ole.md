---
title: Меню и ресурсы (OLE) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ada8731be176368e1503118597fa4d6df38e3ef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378377"
---
# <a name="menus-and-resources-ole"></a>Меню и ресурсы (OLE)

Эта группа статьи описывается использование меню и ресурсы в приложениях MFC OLE документа.

OLE Визуальное редактирование накладывает Дополнительные требования на меню и другие ресурсы, предоставляемые приложения документов OLE, так как существует несколько режимов, в каком контейнере обоих и приложений сервера (компонент) может быть запущена и используется. Например full серверное приложение можно запустить в любом из следующих трех режимов:

- Автономно.

- В месте, для изменения элемента в контексте контейнера.

- Открыта для редактирования элементов вне контекста своего контейнера, часто в отдельном окне.

Для этого требуется три отдельных меню макетов, по одной для каждого из возможных режима приложения. Таблицы сочетаний клавиш необходимы также для каждого нового режима. Приложения-контейнера может поддерживать или не поддерживать активации на месте; в этом случае требуются новую структуру меню и связанные таблицы сочетаний клавиш.

Встроенной активации требует, что контейнер и серверные приложения должны согласовывать пространство панели меню, панели инструментов и состояние. Все ресурсы должны разрабатываться с это в виду. Статья [меню и ресурсы: слияние меню](../mfc/menus-and-resources-menu-merging.md) рассматриваются в этом разделе подробно.

Из-за этих проблем приложения документов OLE, созданного с помощью мастера приложений может иметь до четырех отдельных меню и ресурсы таблицы сочетаний клавиш. Они используются по следующим причинам:

|Имя ресурса|Использовать|
|-------------------|---------|
|IDR_MAINFRAME|Использовать в приложении MDI, если файл не открыт, или в приложении SDI независимо от того, открытые файлы. Это стандартное меню, используемых в приложениях, отличных от OLE.|
|IDR_\<проекта > тип|Используемые в приложениях MDI, если файлы открыты. Используется, когда приложение выполняется как автономный. Это стандартное меню, используемых в приложениях, отличных от OLE.|
|IDR_\<проекта > TYPE_SRVR_IP|Используется на сервере или в контейнере, когда открыт объект на месте.|
|IDR_\<проекта > TYPE_SRVR_EMB|Используется серверным приложением, если объект был открыт без активации на месте.|

Каждый из этих имен ресурсов представляет меню и, как правило, в таблицу сочетаний клавиш. Аналогично схемы можно использовать в приложениях MFC, которые не создаются с помощью мастера приложений.

В следующих статьях рассматриваются темы, относящиеся к контейнерам, серверы и слияние необходимые для реализации встроенной активации меню:

- [Меню и ресурсы. Добавление контейнеров](../mfc/menus-and-resources-container-additions.md)

- [Меню и ресурсы. Добавление серверов](../mfc/menus-and-resources-server-additions.md)

- [Меню и ресурсы. Слияние меню](../mfc/menus-and-resources-menu-merging.md)

## <a name="see-also"></a>См. также

[OLE](../mfc/ole-in-mfc.md)

