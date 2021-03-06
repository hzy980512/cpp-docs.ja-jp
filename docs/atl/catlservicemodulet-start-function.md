---
title: Catlservicemodulet::start 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ef614f4cbc3f097e6f790a49c0b599817f9b59c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849186"
---
# <a name="catlservicemoduletstart-function"></a>Catlservicemodulet::start 関数
サービスが実行される`_tWinMain`呼び出し`CAtlServiceModuleT::WinMain`、この`CAtlServiceModuleT::Start`します。  
  
 `CAtlServiceModuleT::Start` 配列を設定`SERVICE_TABLE_ENTRY`各サービスをそのスタートアップ関数にマップする構造体。 この配列は、Win32 API 関数に渡されます[StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324)します。 1 つの EXE は理論上は、複数のサービスを処理する可能性がありますあり、配列が複数`SERVICE_TABLE_ENTRY`構造体。 現時点では、ただし、ATL によって生成されたサービスがサポートする実行可能ファイルごとにサービスを 1 つだけです。 したがって、配列にはサービス名を含む 1 つのエントリと`_ServiceMain`としてスタートアップ関数。 `_ServiceMain` 静的メンバー関数は、 `CAtlServiceModuleT` 、非静的メンバー関数を呼び出す`ServiceMain`します。  
  
> [!NOTE]
>  エラー`StartServiceCtrlDispatcher`をサービス コントロールへの接続マネージャー (SCM) はほとんど意味をサービスとして、プログラムが実行されていないこと。 この場合、呼び出しプログラム`CAtlServiceModuleT::Run`直接プログラムは、ローカル サーバーとして実行できるようにします。 詳細については、ローカル サーバーとしてプログラムを実行して、次を参照してください。[デバッグのヒント](../atl/debugging-tips.md)します。  
  
## <a name="see-also"></a>関連項目  
 [サービス](../atl/atl-services.md)   
 [Catlservicemodulet::start](../atl/reference/catlservicemodulet-class.md#start)

