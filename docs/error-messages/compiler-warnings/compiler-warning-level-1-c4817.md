---
title: Предупреждение компилятора (уровень 1) C4817 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4817
dev_langs:
- C++
helpviewer_keywords:
- C4817
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e87d602b98fe3f70c29b26c39ebce94026606249
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099568"
---
# <a name="compiler-warning-level-1-c4817"></a>Предупреждение компилятора (уровень 1) C4817

"член": недопустимое использование "." для обращения к этому члену; заменено на "->" компилятором

Использован неверный оператор доступа к члену.

## <a name="example"></a>Пример

Приведенный ниже пример приводит к возникновению предупреждения C4817.

```
// C4817.cpp
// compile with: /clr /W1
using namespace System;
int main() {
   array<Int32> ^ a = gcnew array<Int32>(100);
   Console::WriteLine( a.Length );   // C4817
   Console::WriteLine( a->Length );   // OK
}
```
