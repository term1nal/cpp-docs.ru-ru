---
title: Создание значка или другого изображения (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resources [C++], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43ba8086481ea2a8dde20d06b1dc143b297138f8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378310"
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>Создание значка или другого изображения (редактор изображений для значков)

Можно создать новое изображение (растровое изображение, значок, курсор или панели инструментов), а затем с помощью редактора изображений для настройки внешнего вида. Можно также создать новый растровое изображение на основе [шаблона](../windows/how-to-use-resource-templates.md).

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Чтобы добавить новый ресурс изображения в неуправляемый проект C++

1. В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл, а затем выберите **Вставка ресурса** в контекстном меню. (При наличии существующего ресурса изображения в RC-файл, например курсор, вы можете просто щелкните правой кнопкой мыши **курсор** папку и выберите **вставки курсора** в контекстном меню.)

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В [Вставка ресурса-диалоговое окно](../windows/add-resource-dialog-box.md), выберите тип ресурса изображения, которые вы хотите создать (**точечного рисунка**, например) нажмите кнопку **New**.

   Если знак плюс (**+**) отображается рядом с типом ресурса изображения в **Вставка ресурса** диалоговое окно, это означает, что доступны шаблоны. Щелкните знак «плюс», чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **New**.

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Чтобы добавить новый ресурс изображения в проект в языке программирования .NET

1. В **обозревателе решений**, щелкните правой кнопкой мыши папку проекта (например, `WindowsApplication1`).

2. В контекстном меню, щелкните **добавить**, затем выберите **Добавление нового элемента**.

3. В **категории** области разверните **элементы локального проекта** папку, затем выберите **ресурсы**.

4. В **шаблоны** области, выберите тип ресурса, который вы хотите добавить в проект.

   Ресурс будет добавлен в проект в **обозревателе решений** и ресурс откроется в [редактор изображений](../windows/image-editor-for-icons.md). Теперь все средства, доступные в редакторе изображений можно использовать для изменения образа. Дополнительные сведения о добавлении изображений в управляемый проект см. в разделе [загрузка рисунка во время разработки](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

   > [!NOTE]
   > Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов. Дополнительные сведения см. в разделе [Создание файлов ресурсов](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) в *руководства разработчика .NET Framework*.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[Преобразование растровых изображений в панель инструментов](../windows/converting-bitmaps-to-toolbars.md)<br/>
[Создание панелей инструментов](../windows/creating-new-toolbars.md)<br/>
[Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Редактор изображений для значков](../windows/image-editor-for-icons.md)