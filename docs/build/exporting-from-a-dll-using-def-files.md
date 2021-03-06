---
title: Экспорт из DLL с использованием DEF-файлы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22bcca929d687ef3b10ee65bcb2230c03bfb0a11
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706008"
---
# <a name="exporting-from-a-dll-using-def-files"></a>Экспорт из библиотеки DLL с использованием DEF-файлов

Файл определения модуля (DEF) — это текстовый файл, содержащий один или несколько операторов модуля, описывающих различные атрибуты библиотеки DLL. Если вы не используете **__declspec(dllexport)** ключевое слово для экспорта функций DLL библиотеки DLL потребуется DEF-файла.

Минимальный DEF-файл должен содержать следующие операторы определения модуля:

- Первый оператор в файле должен быть оператор LIBRARY. Этот оператор определяет DEF-файл как принадлежащий библиотеке DLL. Оператор LIBRARY следует имя библиотеки DLL. Компоновщик помещает это имя в DLL-библиотека импорта.

- Оператор EXPORTS перечисляет имена и, при необходимости, порядковые номера функций, экспортируемых посредством библиотеки DLL. Присвоения функции порядкового после имени функции с помощью символа (@) и номер. При указании порядковые номера, они должны быть в диапазоне от 1 до N, где N — число функций, экспортируемых посредством библиотеки DLL. Если вы хотите экспортировать функции по порядковому номеру, см. в разделе [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) а также в этом разделе.

Например библиотеку DLL, которая содержит код для реализации дерева поиска двоичных файлов может выглядеть следующим образом:

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

Если вы используете [мастера MFC DLL](../mfc/reference/mfc-dll-wizard.md) для создания библиотеки DLL MFC, мастер создает скелет DEF-файла и автоматически добавляет его в проект. Добавьте имена функций, которые нужно экспортировать в этот файл. Для не - MFC DLL, необходимо создать DEF-файл самостоятельно и добавить его в проект.

Если при экспорте функции в файле C++, необходимо либо поместить декорированные имена в DEF-файле, либо определить экспортируемые функции с помощью стандартных средств компоновки C с помощью extern «C». Если вам нужно поместить декорированные имена в DEF-файле, их можно получить с помощью [DUMPBIN](../build/reference/dumpbin-reference.md) средство или с помощью компоновщика [/MAP](../build/reference/map-generate-mapfile.md) параметр. Обратите внимание, что декорированные имена, созданные компилятором, зависят от компилятора. Если поместить декорированные имена, созданные компилятором Visual C++ в DEF-файла, приложения, связанные с библиотекой DLL должны также быть построены с использованием той же версии Visual C++, чтобы декорированные имена в вызывающем приложении соответствовали экспортируемым именам в .de библиотеки DLL файл f.

Если вы создаете [библиотеки DLL расширения](../build/extension-dlls-overview.md), экспорт, с помощью DEF-файла, поместите следующий код в начало и конец файлов заголовка, содержащих экспортируемые классы:

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Эти строки убедитесь, что переменные MFC, используемых внутри классов или добавленных к классам, экспортировать или импортировать из библиотеки DLL расширения MFC. Например, при наследовании класса с помощью `DECLARE_DYNAMIC`, макрос расширяется и включает `CRuntimeClass` переменную-член класса. Если исключить эти четыре строки может привести к библиотеки DLL для компиляции или некорректно или привести к ошибке, когда клиентское приложение связано с библиотекой DLL.

При построении библиотеки DLL, компоновщик использует DEF-файл для создания файла экспорта (EXP) и библиотека (.lib) импортируемого файла. Затем компоновщик использует файл экспорта для построения DLL-файла. Исполняемые файлы, которые неявно ссылаются на библиотеку DLL, ссылаются на библиотеку импорта, когда они создаются.

Обратите внимание на то, что MFC использует DEF-файлы для экспорта функций и классов из файла MFCx0.dll.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций C++ для использования в исполняемых файлах языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью объявления __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [DEF-файлы](../build/reference/module-definition-dot-def-files.md)

- [Правила для операторов определения модуля](../build/reference/rules-for-module-definition-statements.md)

- [Декорированные имена](../build/reference/decorated-names.md)

- [Импорт и экспорт встраиваемых функций](../build/importing-and-exporting-inline-functions.md)

- [Взаимный импорт](../build/mutual-imports.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)