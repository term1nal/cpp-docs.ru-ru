---
title: 'Функции Бесселя: _j0, _j1, _jn, _y0, _y1, _yn | Документы Майкрософт'
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
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
- c.bessel
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
dev_langs:
- C++
helpviewer_keywords:
- Bessel functions
- _j0 function
- _j1 function
- _jn function
- _y0 function
- _y1 function
- _yn function
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf461a7737ee1f23650ff80f203524c427fb644d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393606"
---
# <a name="bessel-functions-j0-j1-jn-y0-y1-yn"></a>Функции Бесселя: _j0, _j1, _jn, _y0, _y1, _yn

Вычисляют функцию Бесселя первого или второго типа порядка 0, 1 и n. Функции Бесселя часто используются в математике теории электромагнитных волн.

## <a name="syntax"></a>Синтаксис

```C
double _j0(
   double x
);
double _j1(
   double x
);
double _jn(
   int n,
   double x
);
double _y0(
   double x
);
double _y1(
   double x
);
double _yn(
   int n,
   double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

*n*<br/>
Целочисленный порядок функции Бесселя.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращает функцию Бесселя *x*. Если *x* имеет отрицательное значение в **_y0**, **_y1**, или **_yn** функции, процедура устанавливает **errno** для  **EDOM**, выводит **_DOMAIN** сообщение об ошибке, **stderr**и возвращает **_HUGE_VAL**. Вы можете изменить ошибок с помощью **_matherr**.

## <a name="remarks"></a>Примечания

**_J0**, **_j1**, и **_jn** подпрограммы возвращают Бесселя функции первого типа: порядка 0, 1 и n соответственно.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**НЕДОПУСТИМЫЙ**|**_DOMAIN**|

**_Y0**, **_y1**, и **_yn** подпрограммы возвращают второго типа функции Бесселя: порядка 0, 1 и n соответственно.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**НЕДОПУСТИМЫЙ**|**_DOMAIN**|
|± 0|**ZERODIVIDE**|**_ОДНОТРУБНЫЙ**|
|&#124;x&#124; < 0,0|**НЕДОПУСТИМЫЙ**|**_DOMAIN**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_j0**, **_j1**, **_jn**, **_y0**, **_y1**, **_yn**|\<cmath> (C++), \<math.h> (C, C++)|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_bessel1.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.387;
   int n = 3, c;

   printf( "Bessel functions for x = %f:\n", x );
   printf( "   Kind   Order  Function     Result\n\n" );
   printf( "   First  0      _j0( x )     %f\n", _j0( x ) );
   printf( "   First  1      _j1( x )     %f\n", _j1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );
   printf( "   Second 0      _y0( x )     %f\n", _y0( x ) );
   printf( "   Second 1      _y1( x )     %f\n", _y1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );
}
```

```Output
Bessel functions for x = 2.387000:
   Kind   Order  Function     Result

   First  0      _j0( x )     0.009288
   First  1      _j1( x )     0.522941
   First  2      _jn( 2, x )  0.428870
   First  3      _jn( 3, x )  0.195734
   First  4      _jn( 4, x )  0.063131
   Second 0      _y0( x )     0.511681
   Second 1      _y1( x )     0.094374
   Second 2      _yn( 2, x )  -0.432608
   Second 3      _yn( 3, x )  -0.819314
   Second 4      _yn( 4, x )  -1.626833
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_matherr](matherr.md)<br/>
