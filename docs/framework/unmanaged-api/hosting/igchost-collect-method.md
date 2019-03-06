---
title: IGCHost::Collect メソッド
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 973062e93e4964da0a21c14c17e0ce1960029ebd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489073"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="e9dfc-102">IGCHost::Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="e9dfc-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="e9dfc-103">コレクションの現在のガベージ コレクションの状態に関係なく、特定のジェネレーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="e9dfc-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9dfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="e9dfc-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9dfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9dfc-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e9dfc-106">[in]ガベージ コレクションを生成します。</span><span class="sxs-lookup"><span data-stu-id="e9dfc-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="e9dfc-107">値-1 は、すべてのジェネレーションのガベージ コレクションが行われることを示します。</span><span class="sxs-lookup"><span data-stu-id="e9dfc-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9dfc-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9dfc-108">Requirements</span></span>  
 <span data-ttu-id="e9dfc-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9dfc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9dfc-110">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e9dfc-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e9dfc-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e9dfc-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9dfc-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9dfc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9dfc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9dfc-113">See also</span></span>
- [<span data-ttu-id="e9dfc-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9dfc-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
