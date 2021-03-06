---
title: IEnumOnSTLImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b70e8012d6126b39129cff6fc86366f72459dc02
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883009"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl クラス
このクラスは、C++ 標準ライブラリ コレクションに基づいて列挙子インターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>パラメーター  
 *ベース*  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 *piid*  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 *T*  
 列挙子インターフェイスによって公開される項目の種類。  
  
 *コピー*  
 A[コピー ポリシー クラス](../../atl/atl-copy-policy-classes.md)します。  
  
 *CollType*  
 C++ 標準ライブラリ コンテナー クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|実装[IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)します。|  
|[保ちます](#init)|列挙子を初期化します。|  
|[IEnumOnSTLImpl::Next](#next)|実装[IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)します。|  
|[IEnumOnSTLImpl::Reset](#reset)|実装[IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)します。|  
|[IEnumOnSTLImpl::Skip](#skip)|実装[IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|コレクション内の列挙子の現在位置を表す反復子。|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|列挙するアイテムを保持する C++ 標準ライブラリ コンテナーへのポインター。|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|`IUnknown`コレクションを提供するオブジェクトのポインター。|  
  
## <a name="remarks"></a>Remarks  
 `IEnumOnSTLImpl` C++ 標準ライブラリと互換性のあるコンテナーに列挙されている項目を格納する、COM の列挙子インターフェイスの実装を提供します。 このクラスに似ています、 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)列挙子インターフェイスの実装を提供するクラス、配列に基づいています。  
  
> [!NOTE]
>  参照してください[保ちます](../../atl/reference/ccomenumimpl-class.md#init)の違いの詳細について詳しく`CComEnumImpl`と`IEnumOnSTLImpl`します。  
  
 通常、*いない*このインターフェイスの実装から派生することによって、独自の列挙子クラスを作成する必要があります。 インスタンスを作成するが一般的では、C++ 標準ライブラリ コンテナーに基づく ATL が指定した列挙子を使用する場合は、 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)、またはから派生することによって、列挙子が返すコレクションクラスを作成する[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)します。  
  
 ただし、(たとえば、1 つだけでなく、列挙子インターフェイスのインターフェイスを公開している) カスタム列挙子を提供する必要がある場合は、このクラスから派生することができます。 このような状況で可能性をオーバーライドする必要がありますが、[複製](#clone)独自の実装を提供するメソッド。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="init"></a>  保ちます  
 列挙子を初期化します。  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkForRelease*  
 [in]`IUnknown`保持する必要がアライブ列挙子の有効期間中にオブジェクトのポインター。 このようなオブジェクトが存在しない場合は、NULL を渡します。  
  
 *collection*  
 列挙するアイテムを保持する C++ 標準ライブラリ コンテナーへの参照。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 渡した場合`Init`使用できます、別のオブジェクトのコレクションへの参照が保持されている、 *pUnkForRelease*パラメーターを使用できるように、オブジェクトと保持しているコレクションの列挙子では、その必要がある限りです。  
  
 クライアントに返す列挙子インターフェイスへのポインターを渡す前に、このメソッドを呼び出す必要があります。  
  
##  <a name="clone"></a>  IEnumOnSTLImpl::Clone  
 このメソッドの実装を提供、 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)メソッド型のオブジェクトを作成して`CComEnumOnSTL`、同じコレクションと、現在のオブジェクトで使用される反復子で初期化してにインターフェイスを返す新しく作成されたオブジェクト。  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>パラメーター  
 *ppEnum*  
 [out]新しく作成されたオブジェクトの列挙子インターフェイスは、現在の列挙子から複製します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk  
 `IUnknown`コレクションを提供するオブジェクトのポインター。  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>Remarks  
 このスマート ポインターに渡されるオブジェクトの参照を保持する[保ちます](#init)、残っているアライブ列挙子の有効期間中にことを確認します。  
  
##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection  
 このメンバーは、列挙子インターフェイスの実装を促進するデータを提供するコレクションを指します。  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>Remarks  
 このメンバーを呼び出して[保ちます](#init)します。  
  
##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter  
 このメンバーは、コレクション内の現在位置をマークし、後続の要素に移動するために使用する反復子を保持します。  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>  IEnumOnSTLImpl::Next  
 このメソッドの実装を提供、 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)メソッド。  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>パラメーター  
 *celt*  
 [in]要求された要素の数。  
  
 *rgelt*  
 [out]要素を使用して格納する配列。  
  
 *内*  
 [out]実際に返される要素の数*rgelt*します。 これより小さい*celt*場合よりも少ない*celt*要素がリストに残ります。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="reset"></a>  IEnumOnSTLImpl::Reset  
 このメソッドの実装を提供、 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)メソッド。  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="skip"></a>  IEnumOnSTLImpl::Skip  
 このメソッドの実装を提供、 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)メソッド。  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>パラメーター  
 *celt*  
 [in]スキップする要素の数。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
