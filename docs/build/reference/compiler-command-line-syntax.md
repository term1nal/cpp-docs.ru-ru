---
title: Синтаксис командной строки компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18fb22ba370a447be8cb4cb2fb96633d702a1089
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710304"
---
# <a name="compiler-command-line-syntax"></a>Синтаксис командной строки компилятора

В командной строке компилятора используется следующий синтаксис:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

В следующей таблице описаны входных данных в команду CL.

|Ввод|Значение|
|-----------|-------------|
|*Параметр*|Один или несколько [параметров CL](../../build/reference/compiler-options.md). Обратите внимание, что все параметры применяются ко всем файлам указанного источника. Параметры указываются с косой черты (/) или дефис (-). Если параметр принимает аргумент, документов описания параметр ли пробел между параметром и аргументы. Имена параметров (за исключением параметра/Help) чувствительны к регистру. См. в разделе [порядок параметров CL](../../build/reference/order-of-cl-options.md) Дополнительные сведения.|
|`file`|Имя одного или нескольких файлов исходного кода, OBJ-файлов или библиотек. CL компилирует исходные файлы и передает компоновщику имена OBJ-файлов и библиотек. См. в разделе [синтаксис имен файлов CL](../../build/reference/cl-filename-syntax.md) Дополнительные сведения.|
|*lib*|Одно или несколько имен библиотеки. Компилятор передает эти имена в компоновщик.|
|*командный файл*|Файл, содержащий несколько параметров и имен файлов. См. в разделе [командные файлы компилятора CL](../../build/reference/cl-command-files.md) Дополнительные сведения.|
|*ссылка opt*|Один или несколько [параметры компоновщика](../../build/reference/linker-options.md). Компилятор передает эти параметры компоновщика.|

Можно указать любое количество параметров, имен файлов и библиотеки, до тех пор, пока число символов в командной строке не превышает 1024, ограничение, зависит от операционной системы.

Дополнительные сведения о возвращаемом значении cl.exe, см. в разделе [возвращают значение cl.exe](../../build/reference/return-value-of-cl-exe.md) .

> [!NOTE]
>  Ограничение ввода командной строки, равное 1024 символам остаются неизменными в будущих версиях Windows не гарантируется.

## <a name="see-also"></a>См. также

[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)