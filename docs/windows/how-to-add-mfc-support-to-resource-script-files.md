---
title: '方法: リソース スクリプト ファイルに MFC サポートを追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.add.MFC
dev_langs:
- C++
helpviewer_keywords:
- rc files, adding MFC support
- .rc files, adding MFC support
- MFC, adding support to resource scripts files
- resource script files, adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c0493e630c2b141da1fced6964ffc514c761d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879797"
---
# <a name="how-to-add-mfc-support-to-resource-script-files"></a>方法: リソース スクリプト ファイルに MFC サポートを追加する
通常を使用して Windows 用の MFC アプリケーションを作成する場合、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)ウィザードには、Microsoft Foundation のコア機能を含むファイル (リソース スクリプト (.rc) ファイルを含む) の基本的なセットが生成されますクラス (MFC)。 ただし、MFC ベースでない Windows アプリケーション用の .rc ファイルを編集する場合、MFC フレームワークに固有の以下の機能は利用できません。  
  
-   MFC コード ウィザード (旧称"[MFC ClassWizard](http://msdn.microsoft.com/en-us/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)")  
  
-   メニュー プロンプト文字列  
  
-   コンボ ボックス コントロールの一覧の内容  
  
-   ActiveX コントロールのホスト  
  
 ただし、MFC サポートがない既存の .rc ファイルには、このサポートを追加できます。  
  
### <a name="to-add-mfc-support-to-rc-files"></a>.rc ファイルに MFC サポートを追加するには  
  
1.  リソース スクリプト ファイルを開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [リソース ビュー](../windows/resource-view-window.md)、MFC.rc などのリソース フォルダーを強調表示します。  
  
3.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、設定、 **MFC Mode**プロパティを**True**です。  
  
    > [!NOTE]
    >  このフラグを設定するだけでなく、.rc ファイルを MFC プロジェクトの一部にする必要があります。 などを設定するだけ**MFC Mode**に**True** Win32 で .rc ファイルをプロジェクトには及ばない、MFC 機能のいずれか。  
  

  
 **必要条件**  
  
 MFC  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)