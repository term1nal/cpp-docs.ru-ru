---
title: Ошибка средств компоновщика LNK1179 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d22ebb329d390d44aea44ff9dc6f3bf2f86a1d26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117462"
---
# <a name="linker-tools-error-lnk1179"></a>Ошибка средств компоновщика LNK1179

Недопустимый или поврежденный файл: повторяющийся COMDAT «имя_файла»

Модуль объекта содержит два или более COMDAT с тем же именем.

Эта ошибка может возникнуть при использовании [/H](../../build/reference/h-restrict-length-of-external-names.md), который ограничивает длину внешних имен, и [/Gy](../../build/reference/gy-enable-function-level-linking.md), какие пакеты функций COMDAT.

## <a name="example"></a>Пример

В следующем коде `function1` и `function2` идентичны в первые восемь символов. Компиляция с **/Gy** и **/H8** возникает ошибка компоновки.

```
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```