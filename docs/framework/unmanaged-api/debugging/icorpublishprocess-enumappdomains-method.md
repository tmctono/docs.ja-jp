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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 173a7d6793bec9262efb661d56e3a371d0bf9b47
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986623"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="71ff0-102">ICorPublishProcess::EnumAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="71ff0-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="71ff0-103">これによって参照されているプロセスでアプリケーション ドメインの列挙子を取得します。 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="71ff0-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ff0-104">構文</span><span class="sxs-lookup"><span data-stu-id="71ff0-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71ff0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71ff0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="71ff0-106">[out]アドレスへのポインター、 [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)このプロセスでのアプリケーション ドメインのコレクションを反復処理できるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="71ff0-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71ff0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="71ff0-107">Remarks</span></span>  
 <span data-ttu-id="71ff0-108">アプリケーション ドメインの一覧が存在するアプリケーション ドメインのスナップショットに基づいたとき、`EnumAppDomains`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71ff0-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="71ff0-109">このメソッドは、最新の一覧を作成する 2 回以上呼び出すことがあります。</span><span class="sxs-lookup"><span data-stu-id="71ff0-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="71ff0-110">このメソッドの後続の呼び出しは既存のリストを受けません。</span><span class="sxs-lookup"><span data-stu-id="71ff0-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="71ff0-111">プロセスが終了している場合`EnumAppDomains`CORDBG_E_PROCESS_TERMINATED の HRESULT 値を持つは失敗します。</span><span class="sxs-lookup"><span data-stu-id="71ff0-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ff0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="71ff0-112">Requirements</span></span>  
 <span data-ttu-id="71ff0-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71ff0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ff0-114">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="71ff0-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="71ff0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71ff0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71ff0-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ff0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ff0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="71ff0-117">See also</span></span>

- [<span data-ttu-id="71ff0-118">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71ff0-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
