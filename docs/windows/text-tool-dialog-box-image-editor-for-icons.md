---
title: Диалоговое окно "текст" (C++) (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.texttool
dev_langs:
- C++
helpviewer_keywords:
- text, adding to an image
- Text Tool dialog box [C++]
ms.assetid: a6036ef4-1871-40db-8239-6ddbe8f422f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55ad361c9252cfc4989926f90a9fedfd523c7d9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313454"
---
# <a name="text-tool-dialog-box-c-image-editor-for-icons"></a>Диалоговое окно "текст" (C++) (редактор изображений для значков)

Используйте **текст** диалоговое окно для добавления текста к ресурсу курсор, точечный рисунок или значок.

Чтобы открыть это диалоговое окно, откройте [редактор изображений](../windows/window-panes-image-editor-for-icons.md). Выберите **средства** из **изображение** меню, а затем выберите **текст** команды.

### <a name="font-button"></a>Кнопка шрифта

Открывает [шрифт текста-диалоговое окно](../windows/text-tool-font-dialog-box-image-editor-for-icons.md), в котором можно изменить шрифт, стиль или размер шрифта курсора. Изменения применяются к тексту, отображаемому в **текст** области.

### <a name="text-area"></a>Текстовое поле

Отображает текст, отображаемый как часть ресурса. Изначально область пуста.

> [!NOTE]
> Если **прозрачный фон** не установлен, будут помещены только текст в изображение. Если **непрозрачный фон** имеет значение, ограничивающий прямоугольник, заполненный [цвет фона](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), будут располагаться за текстом. Дополнительные сведения см. в разделе [Выбор непрозрачный и прозрачный фон](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Вы можете щелкнуть **текст** диалоговое окно, чтобы получить доступ к контекстное меню по умолчанию, который содержит список стандартных команд Windows.

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)