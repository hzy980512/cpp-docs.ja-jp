---
title: ビルド イベントの指定 | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs:
- C++
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5940f0d6efaec402a4a85ed659f42d7eab1bf91d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33334965"
---
# <a name="specifying-build-events"></a>ビルド イベントの指定

ビルド開始前、リンク プロセス前、ビルド終了後に実行するコマンドを指定する目的で、ビルド イベントを使用できます。

ビルド イベントは、ビルド プロセスにおいてビルドがこれらのポイントに正常に達した場合にのみ実行されます。 ビルドでエラーが発生した場合、*ビルド後*イベントは発生しません。リンク段階前にエラーが発生した場合、*リンク前*イベントも*ビルド後*イベントも発生しません。 また、ファイルをリンクする必要がない場合、*リンク前*イベントは発生しません。 リンク手順が含まれないプロジェクトでも、*リンク前*イベントを利用できません。

ファイルをビルドする必要がない場合、ビルド イベントは発生しません。

ビルド イベントに関する全般情報については、「[カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)」を参照してください。

### <a name="to-specify-a-build-event"></a>ビルド イベントを指定するには

1. **ソリューション エクスプローラー**で、ビルド イベントを指定するプロジェクトを選択します。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../ide/working-with-project-properties.md)」を参照してください。

1. **[ビルド イベント]** フォルダーで、ビルド イベント プロパティ ページを選択します。

1. ビルド イベントに関連付けられたプロパティを指定します。

   - **[コマンド ライン]** で、コマンド プロンプトの場合と同様にコマンドを指定します。 有効なコマンドまたはバッチ ファイルと必要な入力ファイルまたは出力ファイルがあればそれを指定します。 後続のコマンドがすべて確実に実行されるように、バッチ ファイル名の前に **call** バッチ コマンドを指定します。

      MSBuild マクロを利用すれば、複数の入力ファイルと出力ファイルを数式で指定できます。 ファイルの場所またはファイル セットの名前を指定する方法については、「[Common Macros for Build Commands and Properties](../ide/common-macros-for-build-commands-and-properties.md)」(ビルドのコマンドとプロパティの共通マクロ) を参照してください。

      '%' は MSBuild に予約されている文字です。環境変数を指定する場合、エスケープ文字 **%** をそれぞれ、16 進数エスケープ シーケンス **%25** に変更してください。 たとえば、**%WINDIR%** を **%25WINDIR%25** に変更します。 MSBuild は **%25** シーケンスをそれぞれ **%** 文字に変更し、それから環境変数にアクセスします。

   - **[説明]** には、このイベントの説明を入力します。 このイベントが発生したとき、**[出力]** ウィンドウにこの説明が表示されます。

   - **[ビルドから除外]** には、イベントを実行しない場合、**[はい]** を指定します。

## <a name="see-also"></a>関連項目

[カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)  
[ビルドのコマンドとプロパティの共通マクロ](../ide/common-macros-for-build-commands-and-properties.md)  
[ビルドのカスタマイズのトラブルシューティング](../ide/troubleshooting-build-customizations.md)  
