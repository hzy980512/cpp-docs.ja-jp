---
title: コンパイラの警告 (レベル 4) C4343 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4343
dev_langs:
- C++
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 300bab652c88322ef7e3b28cbf2cafe304d361d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302335"
---
# <a name="compiler-warning-level-4-c4343"></a>コンパイラの警告 (レベル 4) C4343
\#プラグマ optimize("g",off)/Og オプションをオーバーライドします  
  
 この警告 (Itanium プロセッサ ファミリ (IPF) コンパイラでのみ有効) は、pragma [optimize](../../preprocessor/optimize.md) が [/Og](../../build/reference/og-global-optimizations.md) コンパイラ オプションをオーバーライドしたことを報告します。  
  
 次の例では C4343 が生成されます。  
  
```  
// C4343.cpp  
// compile with: /Og /W4 /LD  
// processor: IPF  
#pragma optimize ("g", off)   // C4343  
```