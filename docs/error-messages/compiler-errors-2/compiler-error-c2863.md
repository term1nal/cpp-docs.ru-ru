---
title: Ошибка компилятора C2863 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2863
dev_langs:
- C++
helpviewer_keywords:
- C2863
ms.assetid: 32561d67-a795-486b-b3b6-4b90a1acb176
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4df5c82a14d24a8da1d296ff6f04dd4adcd98a0f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136040"
---
# <a name="compiler-error-c2863"></a>Ошибка компилятора C2863

«интерфейс»: интерфейс не может иметь friends

Не допускается объявление дружественных объектов в интерфейсе.

Следующий пример приводит к возникновению ошибки C2863:

```
// C2863.cpp
// compile with: /c
#include <unknwn.h>

class CMyClass {
   void *f();
};

__interface IMyInterface {
   void g();

   friend int h();   // 2863
   friend interface IMyInterface1;  // C2863
   friend void *CMyClass::f();  // C2863
};
```