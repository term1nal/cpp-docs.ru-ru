---
title: _fdopen, _wfdopen | Документы Майкрософт
ms.custom: ''
ms.date: 12/12/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fdopen
- _wfdopen
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23416e4c6895669e73ec6611cf38c678016c52a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107046"
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen

Связывает поток с файлом, который ранее был открыт для низкоуровневого ввода-вывода.

## <a name="syntax"></a>Синтаксис

```C
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор открытого файла.

*mode*<br/>
Тип доступа к файлу.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на открытый поток. Значение указателя null обозначает ошибку. Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** устанавливается в значение **значение EBADF**, который указывает недопустимый идентификатор файла, или **EINVAL**, что означает, что *режим*  был пустым указателем.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Fdopen** функция связывает поток ввода-вывода с файлом, который определяется параметром *fd*, таким образом обеспечивая файла, открытого для низкоуровневого ввода-вывода возможность буферизации и форматирования. **_wfdopen** — это двухбайтовая версия **_fdopen**; *режим* аргумент **_wfdopen** — строка расширенных символов. **_wfdopen** и **_fdopen** идентично в противном случае.

Переданные дескриптора файла **_fdopen** принадлежат возвращенным **ФАЙЛ &#42;**  потока. Если **_fdopen** прошла успешно, не следует вызывать [ \_закрыть](close.md) на дескриптор файла. Вызов [fclose](fclose-fcloseall.md) возвращенного **ФАЙЛ &#42;**  также закрывает дескриптор файла.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|\_Юникод и \_MBCS не определены|\_Определенные MBCS|\_Определенные ЮНИКОДА|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*Режим* символьная строка указывает тип доступа к файлам, запрошен для файла:

|*mode*|Access|
|-|-|
**"r"**|Открывает для чтения. Если файл не существует или не удается найти, **fopen** вызов завершается ошибкой.
**"w"**|Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.
**"a"**|Открывает для записи в конце файла (Добавление). Создает файл, если он не существует.
**"r+"**|Открывает для чтения и записи. Файл должен существовать.
**"w+"**|Открывает пустой файл для чтения и записи. Если файл существует, его содержимое удаляется.
**"a+"**|Открывается для чтения и добавления. Создает файл, если он не существует.

При открытии файла с **«»** или **«+»** доступ к типу, все операции записи выполняются в конце файла. Указатель файла может быть перемещен с помощью [fseek](fseek-fseeki64.md) или [rewind](rewind.md), но он всегда перемещается обратно в конец файла перед любой записи, операция выполняется. Поэтому перезаписать существующие данные невозможно. Когда **«r +»**, **«w +»**, или **«+»** задан тип доступа, чтение и запись разрешены (файл считается открыт для «обновления»). Однако при переключении между чтением и записью должны быть промежуточные [fflush](fflush.md), [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), или [rewind](rewind.md) операция. Можно указать текущую позицию для [fsetpos](fsetpos.md) или [fseek](fseek-fseeki64.md) операции, если вы хотите.

Помимо вышеуказанных значений, следующие символы также можно включить в *режим* для определения режима преобразования для символов новой строки:

|*режим* модификатор|Поведение|
|-|-|
**t**|Откройте файл в текстовом (переведенном) режиме. В этом режиме сочетания символов возврата каретки и перевода строки (CR-LF) преобразуются в один символ перевода строки (LF) на входе, а символы перевода строки (LF) преобразуются на выходе в сочетания символов возврата каретки и перевода строки (CR-LF). Кроме того, на входе Ctrl+Z интерпретируется как символ конца файла.
**b**|Открыть в двоичном (непреобразованном) режиме. Все преобразования из **t** режим подавляются.
**c**|Включите флажок фиксации для связанного *filename* таким образом, чтобы содержимое файлового буфера записывается непосредственно на диск при вызове **fflush** или **_flushall** вызывается.
**n**|Сбросьте флажок фиксации для связанного *filename* для «без фиксации». Это значение по умолчанию. Оно также переопределяет глобальный флаг фиксации при компоновке программы с COMMODE.OBJ. Значение по умолчанию глобального флага фиксации — "без фиксации", если только программа не скомпонована явно с файлом COMMODE.OBJ.

**t**, **c**, и **n** *режим* представляют собой расширения Майкрософт для **fopen** и **_fdopen**. Не используйте их, если нужно сохранить совместимость с ANSI.

Если **t** или **b** не имеет *режим*, режим преобразования по умолчанию определяется глобальной переменной [ \_fmode](../../c-runtime-library/fmode.md). Если **t** или **b** отмеченную к аргументу, эта функция завершается неудачно и возвращает значение NULL. Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Допустимые символы для *режим* строку, используемую в **fopen** и **_fdopen** соответствуют *oflag* аргументы, используемые в [ \_откройте](open-wopen.md) и [ \_sopen](sopen-wsopen.md), как показано в следующей таблице:

|Символы в *режим* строки|Эквивалентное *oflag* значение **_open** и **_sopen**|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_WRONLY &#124; \_O\_APPEND** (обычно  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O \_APPEND**)|
|**+**|**\_O\_RDWR &#124; \_O\_APPEND** (обычно  **\_O\_RDWR &#124; \_O\_APPEND &#124; \_O\_ Создание СТРУКТУРЫ** )|
|**r**|**\_O\_: RDONLY**|
|**r +**|**\_O\_RDWR**|
|**w**|**\_O\_WRONLY** (обычно  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**w +**|**\_O\_RDWR** (обычно  **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**b**|**\_O\_ДВОИЧНЫЕ**|
|**t**|**\_O\_ТЕКСТА**|
|**c**|Нет|
|**n**|Нет|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crtfdopentxt"></a>Входные данные: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>Вывод

```Output
Lines in file: 2
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[\_Dup, \_dup2](dup-dup2.md)<br/>
[fclose, \_fcloseall](fclose-fcloseall.md)<br/>
[fopen, \_wfopen](fopen-wfopen.md)<br/>
[freopen, \_wfreopen](freopen-wfreopen.md)<br/>
[\_открыть, \_wopen](open-wopen.md)<br/>
