---
title: Ошибка компилятора C3056 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3056
dev_langs:
- C++
helpviewer_keywords:
- C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0495bc9c31df3aa3ff47ef860e8e47ea6f7c2248
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063584"
---
# <a name="compiler-error-c3056"></a>Ошибка компилятора C3056

"символ": символ не находится в одной области с директивой threadprivate

Символ, используемый в предложении [threadprivate](../../parallel/openmp/reference/threadprivate.md) , должен находиться в той же области, что и предложение `threadprivate` .

В следующем примере возникает ошибка C3056.

```
// C3056.cpp
// compile with: /openmp
int x, y;
void test() {
   #pragma omp threadprivate(x, y)   // C3056
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Возможное решение

```
// C3056b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)
void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```