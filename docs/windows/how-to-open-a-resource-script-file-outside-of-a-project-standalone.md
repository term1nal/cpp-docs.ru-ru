---
title: 'Как: открытие файла описания ресурсов за пределами проекта C++ (изолированная версия) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e52d78de0026fa4a589877ee0a591da26107fde
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391547"
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>Как: открытие файла описания ресурсов за пределами проекта C++ (изолированный)

Ресурсы в RC-файле можно просматривать без открытия проекта. RC-файл откроется в окне документа в [представление ресурсов](../windows/resource-view-window.md) окна (как в случае, когда файл открыт в рамках проекта).

> [!NOTE]
> Это важное отличие, так как некоторые команды доступны только в том случае, когда файл открыт отдельно (за пределами проекта). Например, можно сохранить только файл в другом формате или другое имя файла при открытии файла за пределами проекта ( **Сохранить как** команда недоступна, когда файл открыт в проекте).

### <a name="to-open-an-rc-file-outside-a-project"></a>Открытие RC-файла за пределами проекта

1. Из **файл** меню, выберите **откройте**, затем нажмите кнопку **файл**.

2. В **открыть файл** диалоговом окне найдите файл описания ресурсов, вы хотите просмотреть, выделите файл и нажмите кнопку **откройте**.

   > [!NOTE]
   > Если вы откроете проект (**файл**, **откройте**, **проекта**), некоторые команды не будут доступны для вас. Открыть файл "отдельно" означает открыть его без загрузки проекта.

Чтобы открыть и просмотреть файл ресурсов в текстовом формате, см. в разделе [редактирование файла описания ресурсов (RC-файла)](../windows/how-to-open-a-resource-script-file-in-text-format.md).

### <a name="to-open-multiple-rc-files-outside-a-project"></a>Открытие нескольких RC-файлов за пределами проекта

1. Откройте отдельно два файла ресурсов. Например, откройте `Source1.rc` и `Source2.rc`.

   1. Из **файл** меню, выберите **откройте**, затем нажмите кнопку **файл**.

   2. В **открыть файл** диалоговом окне перейдите в первый файл описания ресурсов, которую требуется открыть (`Source1.rc`), выделите его и нажмите кнопку **откройте**.

   3. Повторите предыдущий шаг, чтобы открыть второй RC-файл (`Source2.rc`).

       RC-файлы будут открыты в отдельных окнах документа.

2. Когда будут открыты оба RC-файла, расположите их окна рядом, чтобы можно было просматривать их одновременно:

   - Из **окно** меню, выберите **создать группу горизонтальных вкладок** или **создать группу вертикальных вкладок**.

       \- или -

   - Щелкните правой кнопкой мыши один из RC-файлов и выберите **создать группу горизонтальных вкладок** или **создать группу вертикальных вкладок** в контекстном меню.

> [!NOTE]
> Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Редакторы ресурсов](../windows/resource-editors.md)