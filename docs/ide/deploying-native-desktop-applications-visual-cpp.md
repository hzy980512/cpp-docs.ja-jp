---
title: ネイティブ デスクトップ アプリケーションの配置 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f4aa355c132b4c94f085cbdf7aa73785357d0f0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34259245"
---
# <a name="deploying-native-desktop-applications-visual-c"></a>ネイティブ デスクトップ アプリケーションの配置 (Visual C++)

配置とは、完成したアプリケーションやコンポーネントを他のコンピューターにインストールできるように配布するためのプロセスです。 配置計画は、開発者のコンピューターでアプリケーションが作成されたときから始まります。 そのアプリケーションがユーザーのコンピューターにインストールされ、使用できるようになったときに、配置は終了します。

Visual Studio は、Windows アプリケーションを配置するためのさまざまなテクノロジを提供しています。 これには、ClickOnce による配置と Windows インストーラーによる配置が含まれます。

- ClickOnce は、共通言語ランタイム (CLR) を対象とする C++ アプリケーションの配置に使用できます (混合アセンブリ、純粋アセンブリおよび検証可能アセンブリ)。 マネージド アプリケーションの配置には Windows インストーラーを使用できますが、マニフェスト署名などの .NET Framework のセキュリティ機能が利用できる ClickOnce の使用をお勧めします。 ClickOnce では、ネイティブ C++ アプリケーションの配置はサポートされていません。 詳細については、「 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)」を参照してください。

- Windows インストーラー テクノロジは、ネイティブ C++ アプリケーションに使用することも、CLR を対象とする C++ アプリケーションに使用することもできます。

このドキュメントのこのセクションの記事では、ネイティブ Visual C++ アプリケーションをあらゆるコンピューターで確実に実行する方法について説明するために、サポート対象のターゲット プラットフォーム、インストール パッケージに含める必要があるファイル、アプリケーションに依存するコンポーネントの推奨される再配布方法を示します。

## <a name="in-this-section"></a>このセクションの内容

- [Visual C++ での配置](../ide/deployment-in-visual-cpp.md)

- [配置の概念](../ide/deployment-concepts.md)

- [Visual C++ アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)

- [再配布する DLL の決定](../ide/determining-which-dlls-to-redistribute.md)

- [配置方法の選択](../ide/choosing-a-deployment-method.md)

- [ユニバーサル CRT の配置](universal-crt-deployment.md)。

- [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)

- [配置例](../ide/deployment-examples.md)

- [Web クライアント アプリケーションの再頒布](../ide/redistributing-web-client-applications.md)

- [Visual C++ アプリケーションの ClickOnce 配置](../ide/clickonce-deployment-for-visual-cpp-applications.md)

- [以前のランタイム バージョンでの C++ /clr アプリケーションの実行](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>関連項目

- [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [配置](/dotnet/framework/deployment/index)

- [C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)