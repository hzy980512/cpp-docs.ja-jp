---
title: コンパイラ エラー C3211 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3211
dev_langs:
- C++
helpviewer_keywords:
- C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f7fdcfcb9a3ed3322d1263482b043d717bbcae8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249184"
---
# <a name="compiler-error-c3211"></a>コンパイラ エラー C3211
'explicit specialization': 明示的特殊化は、部分的特殊化の構文を使用しています。代わりに、テンプレート <> を使用してください  
  
 明示的特殊化の形式が正しくありません。  
  
 次の例では C3211 が生成されます。  
  
```  
// C3211.cpp  
// compile with: /LD  
template<class T>  
struct s;  
  
template<class T>  
// use the following line instead  
// template<>  
struct s<int>{};   // C3211  
```