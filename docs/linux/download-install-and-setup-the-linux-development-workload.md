---
title: Установка рабочей нагрузки Linux для проектов C++ в Visual Studio | Документация Майкрософт
description: Скачивание, установка и настройка рабочей нагрузки Linux для проектов C++ в Visual Studio.
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 403f1bcd8634c3f471f34ff1266501de5bf05d52
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601396"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Загрузка, установка и настройка рабочей нагрузки Linux

Visual Studio IDE в Windows можно использовать для создания, редактирования и отладки проектов C++, которые выполняются на физическом компьютере Linux, на виртуальной машине или в [подсистеме Windows для Linux](/windows/wsl/about). Чтобы использовать любой из этих сценариев, установите рабочую нагрузку **Разработка для Linux на C++**.

## <a name="visual-studio-setup"></a>Установка Visual Studio

1. В меню поиска Windows введите "Visual Studio Installer", найдите этот элемент в списке результатов для **приложений** и дважды щелкните его. Когда откроется установщик, щелкните **Изменить** и перейдите на вкладку **Рабочие нагрузки**. Прокрутите вниз до раздела **Другие наборы инструментов** и выберите рабочую нагрузку **Разработка для Linux на C++**.

   ![Рабочая нагрузка "Разработка на Visual C++ для Linux"](media/linuxworkload.png)

1. Если вы используете CMake или нацеливаетесь на платформы Интернета вещей или Embedded, в разделе **Разработка для Linux на C++** перейдите вправо к панели **Сведения об установке**, разверните элемент **Дополнительные компоненты** и выберите нужные компоненты. 

1. Для продолжения установки нажмите кнопку **Изменить**.


## <a name="options-for-creating-a-linux-environment"></a>Варианты создания среды Linux

Если у вас нет компьютера Linux, можно создать виртуальную машину Linux в Azure. Дополнительные сведения см. в статье [Краткое руководство. Создание виртуальной машины под управлением Linux на портале Azure](/azure/virtual-machines/linux/quick-create-portal).

Еще один вариант — активировать в Windows 10 подсистему Windows для Linux. Дополнительные сведения см. в [руководстве по установке Windows 10](/windows/wsl/install-win10).

## <a name="linux-setup"></a>Установка Linux

На целевом компьютере Linux должны быть установлены **openssh-server**, **g++**, **gdb** и **gdbserver** и запущена управляющая программа SSH. **ZIP** необходим для автоматической синхронизации удаленных заголовков на локальном компьютере, чтобы обеспечить поддержку Intellisense. Если эти приложения отсутствуют, их можно установить следующим образом.

1. В командной строке оболочки на компьютере Linux выполните следующую команду:

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   Для выполнения команды sudo вам может быть предложено ввести пароль учетной записи root.  Введите его и продолжите.  После завершения эти службы и инструменты будут установлены.

1. Запустите службу ssh на компьютере Linux, выполнив следующую команду:

   `sudo service ssh start`

   Эта команда запустит службу в фоновом режиме для готовности к принятию подключений.
