---
title: __invlpg | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01a35d110c56bba6b89c5bf34dedec61bde90794
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403218"
---
# <a name="invlpg"></a>__invlpg

**Блок, относящийся только к системам Microsoft**

Создает x86 `invlpg` инструкции, что делает недействительным буфера ассоциативной трансляции (TLB) для страницы, связанные с объемом памяти, на которые указывают `Address`.

## <a name="syntax"></a>Синтаксис

```
void __invlpg(
   void* Address
);
```

#### <a name="parameters"></a>Параметры

*Адрес*<br/>
[in] 64-разрядный адрес.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Встроенная `__invlpg` выдает привилегированной инструкции и доступна только в режиме ядра с уровнем привилегий (CPL) 0.

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)