---
title: コンパイラの警告 (レベル 1) C4272 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4272
dev_langs:
- C++
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6de736c3226a9d3377769b65604a458c08e25df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277200"
---
# <a name="compiler-warning-level-1-c4272"></a>コンパイラの警告 (レベル 1) C4272
'function': _declspec; がマークされています。関数をインポートするときに、ネイティブな呼び出し規約を指定する必要があります。  
  
 マークされた関数をエクスポートすると、エラーは、 [_ _clrcall](../../cpp/clrcall.md)マークされた関数をインポートしようとする場合、この警告を発行呼び出し規約、およびコンパイラ`__clrcall`です。  
  
 次の例では、C4272 が生成されます。  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```