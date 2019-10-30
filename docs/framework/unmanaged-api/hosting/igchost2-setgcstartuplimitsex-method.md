---
title: IGCHost2::SetGCStartupLimitsEx メソッド
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
ms.openlocfilehash: d78f81093e61c40eaec334f957d8583eeb593f5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134818"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="172a6-102">IGCHost2::SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="172a6-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="172a6-103">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="172a6-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="172a6-104">構文</span><span class="sxs-lookup"><span data-stu-id="172a6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="172a6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="172a6-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="172a6-106">からガベージコレクションシステムによって使用されるセグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="172a6-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="172a6-107">からジェネレーション0の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="172a6-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="172a6-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="172a6-108">Remarks</span></span>  
 <span data-ttu-id="172a6-109">`SetGCStartupLimitsEx` 設定する値は、ホストを開始する前にのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="172a6-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="172a6-110">これらの値は後で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="172a6-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="172a6-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="172a6-111">Requirements</span></span>  
 <span data-ttu-id="172a6-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="172a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="172a6-113">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="172a6-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="172a6-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="172a6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="172a6-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="172a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172a6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="172a6-116">See also</span></span>

- [<span data-ttu-id="172a6-117">IGCHost2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="172a6-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
