---
title: IObjectSafetyImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f474c73a63c7eaeb7452e88812180a24d1321df
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881189"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl クラス
このクラスの既定の実装を提供する、`IObjectSafety`クライアントを取得し、オブジェクトの安全性レベルを設定できるようにするインターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IObjectSafetyImpl`します。  
  
 *dwSupportedSafety*  
 コントロールのサポートされている安全性のオプションを指定します。 次のいずれかの値になります。  
  
- INTERFACESAFE_FOR_UNTRUSTED_CALLER で識別されるインターフェイス、 [SetInterfaceSafetyOptions](#setinterfacesafetyoptions)パラメーター`riid`スクリプトに対して安全で行う必要があります。  
  
- INTERFACESAFE_FOR_UNTRUSTED_DATA で識別されるインターフェイス、`SetInterfaceSafetyOptions`パラメーター`riid`に信頼されていないデータの安全な初期化中にします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|現在設定されて、オブジェクトの安全性のオプションと同様に、オブジェクトでサポートされている安全性のオプションを取得します。|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|オブジェクトを初期化またはスクリプトに対して安全になります。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|オブジェクトの現在の安全性レベルを格納します。|  
  
## <a name="remarks"></a>Remarks  
 クラス`IObjectSafetyImpl`の既定の実装を提供します。`IObjectSafety`します。 `IObjectSafety`インターフェイスにより、クライアントは、オブジェクトの安全性レベルの設定を取得します。 たとえば、web ブラウザーを呼び出すことができます`IObjectSafety::SetInterfaceSafetyOptions`初期化に対して安全またはスクリプトを実行して安全なコントロールを作成します。  
  
 使用して、 [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category)マクロ CATID_SafeForScripting と CATID_SafeForInitializing コンポーネントのカテゴリが別のコンポーネントは安全であることを指定する方法を提供します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>  IObjectSafetyImpl::GetInterfaceSafetyOptions  
 現在設定されて、オブジェクトの安全性のオプションと同様に、オブジェクトでサポートされている安全性のオプションを取得します。  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Remarks  
 実装のオブジェクトの実装でサポートされている任意のインターフェイスの適切な値を返します`IUnknown::QueryInterface`します。  
  
> [!IMPORTANT]
>  任意のオブジェクトをサポートする`IObjectSafety`は自身のセキュリティと任意のオブジェクトのデリゲートを担当します。 プログラマする必要があります、ユーザーのコンテキストでコードを実行してから発生した問題を考慮、クロスサイト スクリプティングおよび適切なゾーン チェックを実行します。  
  
 参照してください[IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) Windows SDK にします。  
  
##  <a name="m_dwcurrentsafety"></a>  IObjectSafetyImpl::m_dwCurrentSafety  
 オブジェクトの現在の安全性レベルを格納します。  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>  IObjectSafetyImpl::SetInterfaceSafetyOptions  
 により、オブジェクトを設定してスクリプトまたは初期化の安全な[m_dwCurrentSafety](#m_dwcurrentsafety)適切な値のメンバー。  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Remarks  
 実装では、E_NOINTERFACE を返しますのすべてのインターフェイスのオブジェクトの実装でサポートされていない`IUnknown::QueryInterface`します。  
  
> [!IMPORTANT]
>  任意のオブジェクトをサポートする`IObjectSafety`は自身のセキュリティと任意のオブジェクトのデリゲートを担当します。 プログラマする必要があります、ユーザーのコンテキストでコードを実行してから発生した問題を考慮、クロスサイト スクリプティングおよび適切なゾーン チェックを実行します。  
  
 参照してください[IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IObjectSafety インターフェイス](https://msdn.microsoft.com/library/aa768224.aspx)   
 [クラスの概要](../../atl/atl-class-overview.md)
