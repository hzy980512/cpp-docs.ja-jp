---
title: プロパティ ページ (ATL) の指定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ISpecifyPropertyPages
dev_langs:
- C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7119dca24a6b6ec5b66e52d7e2c01cd66985e764
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848377"
---
# <a name="specifying-property-pages"></a>プロパティ ページの指定
ActiveX コントロールを作成するときに、コントロールのプロパティを設定するために使用するプロパティ ページに関連付けるには多くの場合、します。 コンテナーの使用を制御する、`ISpecifyPropertyPages`インターフェイスについては、コントロールのプロパティを設定するプロパティ ページを使用できます。 コントロールでこのインターフェイスを実装する必要があります。  
  
 実装する`ISpecifyPropertyPages`ATL を使用して、次の手順を実行します。  
  
1.  クラスを派生[ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)します。  
  
2.  エントリを追加`ISpecifyPropertyPages`クラスの COM マップにします。  
  
3.  追加、 [PROP_PAGE](reference/property-map-macros.md#prop_page)コントロールに関連付けられた各ページのプロパティ マップするエントリ。  
  
> [!NOTE]
>  使用して、標準のコントロールを生成するときに、 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)、プロパティ マップに PROP_PAGE エントリを追加する必要がありますのみです。 ウィザードでは、他の手順に必要なコードを生成します。  
  
 コンテナーが正常に動作するプロパティ マップ PROP_PAGE エントリと同じ順序で指定したプロパティ ページが表示されます。 一般に、ユーザーが最初に、コントロールに固有のページを参照しているためは、プロパティ マップで、カスタム ページのエントリの後にページの標準的なプロパティ エントリを配置する必要があります。  
  
## <a name="example"></a>例  
 予定表の次のクラスが使用を制御、`ISpecifyPropertyPages`独自の日付のページと素材の色 ページを使用してそのプロパティを設定できるコンテナーを指示するインターフェイス。  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [例](../visual-cpp-samples.md)

