---
title: _bstr_t::_bstr_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::_bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54b61c6aa00a7ea9abf4892e6c3b8568284bd08f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056447"
---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t

**Блок, относящийся только к системам Microsoft**

Создает объект `_bstr_t`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t( ) throw( ); 
_bstr_t(
   const _bstr_t& s1
) throw( );
_bstr_t(
   const char* s2
);
_bstr_t(
   const wchar_t* s3
);
_bstr_t(
   const _variant_t& var
);
_bstr_t(
   BSTR bstr,
   bool fCopy
);
```

#### <a name="parameters"></a>Параметры

*s1*<br/>
Копируемый объект `_bstr_t`.

*s2*<br/>
Многобайтовая строка.

*S3*<br/>
Строка Юникода.

*var*<br/>
Объект [_variant_t](../cpp/variant-t-class.md) объекта.

*BSTR*<br/>
Существующий объект `BSTR`.

*fCopy*<br/>
Если значение равно FALSE, *bstr* аргумент подключен к новому объекту без создания копии путем вызова `SysAllocString`.

## <a name="remarks"></a>Примечания

В следующей таблице описываются конструкторы объекта `_bstr_t`.

|Конструктор|Описание|
|-----------------|-----------------|
|`_bstr_t( )`|Создает значение по умолчанию `_bstr_t` объекта, который инкапсулирует неопределенный `BSTR` объекта.|
|`_bstr_t( _bstr_t&`  `s1`  `)`|Создает объект `_bstr_t` как копию другого объекта.<br /><br /> Это *неполную* копия, которая увеличивает счетчик ссылок инкапсулированного `BSTR` объекта, а не создавать новую.|
|`_bstr_t( char*`  `s2`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.<br /><br /> Этот конструктор конструктор сначала преобразует многобайтовую строку в строку Юникода.|
|`_bstr_t( wchar_t*`  `s3`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.|
|`_bstr_t( _variant_t&`  `var`  `)`|Создает объект `_bstr_t` из объекта `_variant_t`, предварительно получив объект `BSTR` из инкапсулированного объекта VARIANT.|
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Создает объект `_bstr_t` из существующего объекта `BSTR` (а не из строки `wchar_t*`). Если *fCopy* имеет значение false, предоставленного `BSTR` подключен к новому объекту без создания новой копии с `SysAllocString`.<br /><br /> С помощью этого конструктора функции-оболочки в заголовках библиотек типов инкапсулируют и получают право владения объектом `BSTR`, который был возвращен методом интерфейса.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)<br/>
[Класс _variant_t](../cpp/variant-t-class.md)