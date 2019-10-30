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
ms.openlocfilehash: e20ea6addc1ae3f99b4b3d65f532e0128ac160b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134967"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="41931-102">IGCHost::Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="41931-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="41931-103">現在のガベージコレクションの状態に関係なく、指定したジェネレーションに対して強制的にコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="41931-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41931-104">構文</span><span class="sxs-lookup"><span data-stu-id="41931-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41931-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41931-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="41931-106">からガベージコレクションを実行する生成。</span><span class="sxs-lookup"><span data-stu-id="41931-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="41931-107">値-1 は、すべてのジェネレーションがガベージコレクションを実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="41931-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41931-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="41931-108">Requirements</span></span>  
 <span data-ttu-id="41931-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41931-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41931-110">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="41931-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="41931-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="41931-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41931-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41931-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41931-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="41931-113">See also</span></span>

- [<span data-ttu-id="41931-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41931-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
