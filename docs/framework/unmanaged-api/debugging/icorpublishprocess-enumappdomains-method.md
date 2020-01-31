---
title: ICorPublishProcess::EnumAppDomains メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: 4799c1d04e8172c604eeec50f2b841a6db063949
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790580"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="4924c-102">ICorPublishProcess::EnumAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="4924c-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="4924c-103">この[ICorPublishProcess](icorpublishprocess-interface.md)によって参照されるプロセス内のアプリケーションドメインの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="4924c-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4924c-104">構文</span><span class="sxs-lookup"><span data-stu-id="4924c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4924c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4924c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4924c-106">入出力このプロセス内のアプリケーションドメインのコレクションを反復処理できる[ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4924c-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4924c-107">コメント</span><span class="sxs-lookup"><span data-stu-id="4924c-107">Remarks</span></span>  
 <span data-ttu-id="4924c-108">アプリケーションドメインの一覧は、`EnumAppDomains` メソッドが呼び出されたときに存在するアプリケーションドメインのスナップショットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="4924c-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="4924c-109">このメソッドは、新しい最新の一覧を作成するために複数回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4924c-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="4924c-110">既存のリストは、このメソッドの後続の呼び出しの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="4924c-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="4924c-111">プロセスが終了した場合、`EnumAppDomains` は HRESULT 値 CORDBG_E_PROCESS_TERMINATED で失敗します。</span><span class="sxs-lookup"><span data-stu-id="4924c-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4924c-112">要件</span><span class="sxs-lookup"><span data-stu-id="4924c-112">Requirements</span></span>  
 <span data-ttu-id="4924c-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4924c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4924c-114">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="4924c-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4924c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4924c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4924c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4924c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4924c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4924c-117">See also</span></span>

- [<span data-ttu-id="4924c-118">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4924c-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
