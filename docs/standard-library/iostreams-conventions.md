---
title: Соглашения iostreams | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37ba52981f317ff9929a820c42d35cde0506256f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846458"
---
# <a name="iostreams-conventions"></a>Соглашения iostreams

Заголовки iostreams поддерживают преобразования между текстом и закодированными формами, а также ввод и вывод во внешние файлы.

|||
|-|-|
|[\<fstream>](../standard-library/fstream.md)|[\<iomanip>](../standard-library/iomanip.md)|
|[\<ios>](../standard-library/ios.md)|[\<iosfwd>](../standard-library/iosfwd.md)|
|[\<iostream>](../standard-library/iostream.md)|[\<istream>](../standard-library/istream.md)|
|[\<ostream>](../standard-library/ostream.md)|[\<sstream>](../standard-library/sstream.md)|
|[\<streambuf>](../standard-library/streambuf.md)|[\<strstream>](../standard-library/strstream.md)|

В самом простом способе использования iostreams достаточно включить заголовок [\<iostream>](../standard-library/iostream.md). После этого можно извлечь значения из [cin](../standard-library/iostream.md#cin) или [wcin](../standard-library/iostream.md#wcin) для чтения из стандартного ввода. Правила для этого приведены в описании класса [basic_istream](../standard-library/basic-istream-class.md). Вы также можете вставить значения в [cout](../standard-library/iostream.md#cout) или [wcout](../standard-library/iostream.md#wcout) для записи в стандартный вывод. Правила для этого приведены в описании класса [basic_ostream](../standard-library/basic-ostream-class.md). Контроль формата для средств извлечения и средств вставки выполняется с помощью класса [класс basic_ios](../standard-library/basic-ios-class.md). Обработка этой информации о формате извлекающих и вставляющих объектов относится к области нескольких манипуляторов.

Вы можете выполнить те же операции iostreams с файлами, которые вы открываете по имени, с помощью классов, объявленных в [\<fstream>](../standard-library/fstream.md). Для преобразования между iostreams и объектами класса [basic_string Class](../standard-library/basic-string-class.md) используйте классы, объявленные в [\<sstream>](../standard-library/sstream.md). Чтобы сделать то же самое со строками C, используйте классы, объявленные в [\<strstream>](../standard-library/strstream.md).

Остальные заголовки обеспечивают вспомогательные службы, обычно интересные только самым опытным пользователям классов iostreams.

## <a name="see-also"></a>См. также

[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
