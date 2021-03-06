---
title: log2, log2f, log2l | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- log2
- log2l
- log2f
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
dev_langs:
- C++
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16fb56b1a3aef56e201d469974c5de434a08aa41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399531"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Определяет двоичный логарифм (по основанию 2) для указанного значения.

## <a name="syntax"></a>Синтаксис

```C
double log2(
   double x
);

float log2(
   float x
); //C++ only

long double log2(
   long double x
); //C++ only

float log2f(
   float x
);

long double log2l(
   long double x
);

```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение, для которого вычисляется логарифм по основанию 2.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращает log2 *x*.

В случае неудачи может возвращать одно из следующих значений:

|Проблеми|Назад|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ±0|-INFINITY|
|*x* = 1|+0|
|+INFINITY|+INFINITY|
|NaN|NaN|
|ошибка домена|NaN|
|Ошибка полюса|-HUGE_VAL, -HUGE_VALF или -HUGE_VALL|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Если x является целым числом, функция фактически возвращает отсчитываемый от нуля индекс наиболее значимого бита 1 *x*.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**LOG2**, **log2f**, **log2l**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
