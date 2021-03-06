---
title: 関数の宣言と定義の廃止された形式 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- old style function declarations
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d7bb117ff75ae96c8cfa7041534ed0696ad03e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384282"
---
# <a name="obsolete-forms-of-function-declarations-and-definitions"></a>関数の宣言と定義の廃止された形式
旧形式の関数宣言と関数定義では、ANSI C 標準で推奨される構文とは若干異なる規則を使用してパラメーターが宣言されます。 まず、旧形式の宣言にはパラメーター リストがありません。 次に、関数定義では、パラメーターはリストされますが、その型はパラメーター リストで宣言されません。 型宣言は、関数本体を構成する複合ステートメントの前に置かれます。 旧形式の構文は廃止されているため、新しいコードでは使用しないでください。 ただし、旧形式の構文を使用したコードも、引き続きサポートされます。 この例は、旧形式の宣言と定義を示しています。  
  
```  
double old_style();           /* Obsolete function declaration */  
  
double alt_style( a , real )  /* Obsolete function definition */  
    double *real;   
    int a;   
{  
    return ( *real + a ) ;  
}  
```  
  
 整数、または `int` と同じサイズのポインターを返す関数に、宣言は不要ですが、宣言することをお勧めします。  
  
 ANSI C 標準に準拠するために、省略記号を使った旧形式の関数宣言では、/Za オプションでのコンパイル時にエラーが、/Ze オプションでのコンパイル時にはレベル 4 の警告が発生するようになりました。 例:  
  
```  
void funct1( a, ... )  /* Generates a warning under /Ze or */  
int a;                 /* an error when compiling with /Za */  
{  
}  
```  
  
 この宣言は、プロトタイプとして次のように書き直す必要があります。  
  
```  
void funct1( int a, ... )  
{  
}  
```  
  
 旧形式の関数宣言では、その後、省略記号または上位変換された型と同じでない型のパラメーターで同じ関数を宣言または定義した場合にも、警告が発生します。  
  
 次のセクション「[C 関数定義](../c-language/c-function-definitions.md)」では、旧形式の構文を含む関数定義の構文を示します。 旧形式の構文のパラメーター リストの非終端要素は、*identifier-list* です。  
  
## <a name="see-also"></a>参照  
 [関数の概要](../c-language/overview-of-functions.md)