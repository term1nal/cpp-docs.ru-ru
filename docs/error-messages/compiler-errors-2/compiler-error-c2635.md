---
title: Ошибка компилятора C2635 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2635
dev_langs:
- C++
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb7bc7b39550df7b742b2a8b940a77170e81914c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017395"
---
# <a name="compiler-error-c2635"></a>Ошибка компилятора C2635

не удается преобразовать «идентификатор1 *» в "идентификатор2\*"; предполагается преобразование из виртуального базового класса

Процесс преобразования требует приведения к типу из `virtual` базового класса в производном классе, что не допускается.

Следующий пример приводит к возникновению ошибки C2635:

```
// C2635.cpp
class B {};
class D : virtual public B {};
class E : public B {};

int main() {
   B b;
   D d;
   E e;

   D * pD = &d;
   E * pE = &e;
   pD = (D*)&b;   // C2635
   pE = (E*)&b;   // OK
}
```