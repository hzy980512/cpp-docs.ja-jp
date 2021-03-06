---
title: freopen_s、_wfreopen_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfreopen_s
- freopen_s
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
apitype: DLLExport
f1_keywords:
- freopen_s
- _tfreopen_s
- _wfreopen_s
dev_langs:
- C++
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04b136a46672838fd6ee554668353d92796abc7e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405550"
---
# <a name="freopens-wfreopens"></a>freopen_s、_wfreopen_s

ファイル ポインターを再度割り当てます。 これらのバージョンの [freopen、_wfreopen](freopen-wfreopen.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。

## <a name="syntax"></a>構文

```C
errno_t freopen(
   FILE** pFile,
   const char *path,
   const char *mode,
   FILE *stream
);
errno_t _wfreopen(
   FILE** pFile,
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
呼び出しが提供するファイル ポインターへのポインター。

*path*<br/>
新しいファイル パス。

*モード*<br/>
アクセス許可の種類。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

これらの関数はエラー コードを返します。 エラーが発生した場合、元のファイルは閉じられます。

## <a name="remarks"></a>コメント

**Freopen_s**関数が現在関連付けられているファイルを閉じます*ストリーム*し再割り当て*ストリーム*によって指定されたファイルに*パス*. **_wfreopen_s**のワイド文字バージョンは、 **、現在**;*パス*と*モード*引数 **_wfreopen_s**はワイド文字列です。 **_wfreopen_s**と**現在**それ以外の場合の動作は同じです。

いずれかの*pFile*、*パス*、*モード*、または*ストリーム*は**NULL**、または*パス* 、空の文字列には」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**返す**EINVAL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**freopen_s**は通常、既に開いているファイルをリダイレクトする使用**stdin**、 **stdout**、および**stderr**ユーザーによって指定されたファイルにします。 関連付けられている新しいファイル*ストリーム*でが開きます。*モード*、どのファイルは、次のように要求されるアクセスの種類を指定する文字の文字列です。

|*モード*|アクセス|
|-|-|
**"r"**|読み取り用に開きます。 ファイルが存在しないかを検出できない場合、 **freopen_s**呼び出しは失敗します。
**"w"**|書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。
**"a"**|末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。
**"r+"**|読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。
**"w+"**|読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。
**"a+"**|読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。

使用して、 **"w"** と **「w +」** 既存のファイルを破棄するための型は注意します。

使用するファイルを開くと、 **"a"** または **「a +」** アクセスの種類、すべての書き込み、ファイルの最後の操作が発生します。 使用して、ファイル ポインターを移動できます[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)、ファイル ポインターは必ず戻さファイルの末尾には、書き込み操作の前にします。したがって、既存のデータは上書きされません。

**"A"** モードでは、ファイルに追加する前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 **「A +」** モードでファイルに追加する前に EOF マーカーは削除します。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 **「A +」** モードが CTRL + Z EOF マーカーで終了するストリーム ファイルを追加するために必要です。

ときに、 **「r +」**、 **「w +」**、または **「a +」** アクセスの種類を指定すると、読み取りと書き込みの両方が許可されている (ファイルは「更新」開いていると考えられます)。 ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](fsetpos.md)、[fseek](fseek-fseeki64.md)、または [rewind](rewind.md) のいずれかの関数を実行する必要があります。 現在の位置を指定することができます、 [fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)必要な場合は、操作します。 上記の値に加え、次の文字のいずれかに含めることは、*モード*改行の変換モードを指定する文字列。

|*モード*修飾子|変換モード|
|-|-|
**t**|ファイルをテキスト (変換) モードで開きます。
**b**|ファイルをバイナリ (無変換) モードで開きます。キャリッジ リターンとライン フィードの変換は行われません。

テキスト (変換) モードでは、復帰と改行 (CR-LF) の組み合わせは入力; 上の 1 つの改行 (LF) 文字に変換します。LF 文字は、出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りと書き込みの読み取り用または開かれたファイルに **「a +」**、ランタイム ライブラリは、ファイルの末尾に CTRL + Z をチェックし、可能であれば、それを削除します。 これは、使用するため[fseek](fseek-fseeki64.md)と[ftell](ftell-ftelli64.md)ファイル内で移動する場合があります[fseek](fseek-fseeki64.md)が、ファイルの末尾付近に正しく動作します。 **T**オプションは、ANSI 互換が必要な場合は使用できません、Microsoft 拡張機能です。

場合**t**または**b**には、指定しない*モード*、既定の変換モードがグローバル変数によって定義されている[_fmode](../../c-runtime-library/fmode.md)です。 場合**t**または**b**は先頭に、引数、関数が失敗して返します**NULL**です。

テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**freopen_s**|\<stdio.h>|
|**_wfreopen_s**|\<stdio.h> または \<wchar.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_freopen_s.c
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   errno_t err;
   // Reassign "stderr" to "freopen.out":
   err = freopen_s( &stream, "freopen.out", "w", stderr );

   if( err != 0 )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
