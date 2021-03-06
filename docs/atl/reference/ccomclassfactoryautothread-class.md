---
title: CComClassFactoryAutoThread クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a38f3320a507b8bd4ce3095ed2c7a02b7bf573
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883061"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread クラス
このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイス、およびオブジェクトを複数のアパートメントを作成できます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|指定した CLSID のオブジェクトを作成します。|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|  
  
## <a name="remarks"></a>Remarks  
 `CComClassFactoryAutoThread` ような[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)が複数のアパートメント内に作成するオブジェクトを許可します。 このサポートを利用する、EXE のモジュールから派生させる[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)、宣言する[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactoryAutoThread`、指定、 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)オブジェクトのクラス定義でマクロ。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance  
 指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkOuter*  
 [in]かどうか、オブジェクトがの作成、集計の一部として、 *pUnkOuter*不明な外部にある必要があります。 それ以外の場合、 *pUnkOuter* NULL にする必要があります。  
  
 *riid*  
 [in]要求されたインターフェイスの IID。 場合*pUnkOuter* NULL 以外の場合は、 *riid*あります`IID_IUnknown`します。  
  
 *ppvObj*  
 [out]によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObj* NULL に設定されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 モジュールがから派生している場合[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)、`CreateInstance`スレッドに関連付けられているアパートメント オブジェクトを作成する、最初に選択します。  
  
##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer  
 インクリメントおよびデクリメントはモジュールのロックを呼び出すことによってカウント`_Module::Lock`と`_Module::Unlock`、それぞれします。  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>パラメーター  
 *群れ*  
 [in]TRUE の場合、ロック数がインクリメントされます。それ以外の場合、ロック数は減少します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 使用する場合`CComClassFactoryAutoThread`、`_Module`は通常のグローバル インスタンスを指します[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 呼び出す`LockServer`により、クライアントは複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持します。  
  
## <a name="see-also"></a>関連項目  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)
