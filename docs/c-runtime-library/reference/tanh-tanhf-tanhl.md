---
title: TANH, tanhf, tanhl | Документы Microsoft
ms.custom: ''
ms.date: 04/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tanh
- tanhf
- tanhl
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
f1_keywords:
- tanh
- tanhf
- tanhl
- _tanhl
dev_langs:
- C++
helpviewer_keywords:
- tanhl function
- _tanhl function
- tanh function
- tanhf function
- trigonometric functions
- hyperbolic functions
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 438c587099edafedbb2cc3feb4b3a285aa155a0d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408524"
---
# <a name="tanh-tanhf-tanhl"></a>TANH, tanhf, tanhl

Вычисляет гиперболический тангенс.

## <a name="syntax"></a>Синтаксис

```C
double tanh( double x );
float tanhf( float x );
long double tanhl( long double x );
```

```cpp
float tanh( float x );  // C++ only
long double tanh( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Угол в радианах.

## <a name="return-value"></a>Возвращаемое значение

**Tanh** функции возвращают гиперболический тангенс *x*. Ошибка не возвращается.

|Ввод|Исключение SEH|**Matherr** исключение|
|-----------|-------------------|-------------------------|
|± QNAN,IND|Нет|_DOMAIN|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **tanh** , принимающие и возвращающие **float** или **длинные** **двойные** значения. В программе на языке C **tanh** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C)|
|-------------|---------------------|-|
|**TANH**, **tanhf**, **tanhl**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_tanh.c
// This program displays the tangent of pi / 4
// and the hyperbolic tangent of the result.
// Compile by using: cl crt_tanh.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = tan( pi / 4 );
   y = tanh( x );
   printf( "tan( %f ) = %f\n", pi/4, x );
   printf( "tanh( %f ) = %f\n", x, y );
}
```

```Output
tan( 0.785398 ) = 1.000000
tanh( 1.000000 ) = 0.761594
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
