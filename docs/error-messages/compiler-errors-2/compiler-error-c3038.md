---
title: Ошибка компилятора C3038 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3038
dev_langs:
- C++
helpviewer_keywords:
- C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dfdfe8ce50765bf4f94bff7acb0837ddb3fd8ca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057994"
---
# <a name="compiler-error-c3038"></a>Ошибка компилятора C3038

"переменная": переменная в предложении private не может быть редукционной переменной в охватывающем контексте

Переменная, используемая в предложении [reduction](../../parallel/openmp/reference/reduction.md) параллельной директивы, не может быть указана в предложении [private](../../parallel/openmp/reference/private-openmp.md) в директиве распределения рабочей нагрузки, которая привязывается к параллельной конструкции.

Следующий пример приводит к возникновению ошибки C3038:

```
// C3038.cpp
// compile with: /openmp /c
int g_i, g_i2;

int main() {
   int i;

   #pragma omp parallel reduction(+: g_i)
   {
      #pragma omp for private(g_i)   // C3038
      // try the following line instead
      // #pragma omp for private(g_i2)
      for (i = 0; i < 10; ++i)
         g_i += i;
   }
}
```