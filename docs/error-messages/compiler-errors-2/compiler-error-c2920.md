---
title: Ошибка компилятора C2920 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd8d28cf0f201b3042fe3d7a13d28e56150c976e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021607"
---
# <a name="compiler-error-c2920"></a>Ошибка компилятора C2920

переопределение: class: шаблон класса или универсальный тип уже объявлен type

Универсальный класс или класс-шаблон имеет несколько объявлений, которые не эквивалентны. Чтобы устранить эту ошибку, используйте разные имена для различных типов или удалите переопределение имени типа.

В следующем примере показано возникновение ошибки C2920 и приводятся сведения по ее устранению.

```
// C2920.cpp
// compile with: /c
typedef int TC1;
template <class T>
struct TC1 {};   // C2920
struct TC2 {};   // OK - fix by using a different name
```

Ошибка C2920 также может возникнуть при использовании универсальных шаблонов:

```
// C2920b.cpp
// compile with: /clr /c
typedef int GC1;
generic <class T>
ref struct GC1 {};   // C2920
ref struct GC2 {};   // OK - fix by using a different name
```