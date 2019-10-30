---
title: IGCHost::SetGCStartupLimits メソッド
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 1ae50fb3ff15097f9a6ca5839f3832bcfc58d3f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134856"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="29886-102">IGCHost::SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="29886-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="29886-103">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="29886-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="29886-104">.NET Framework 4.5 以降では、 [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)メソッドを使用して、セグメントサイズと最大ジェネレーション0のサイズを `DWORD` より大きい値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="29886-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29886-105">構文</span><span class="sxs-lookup"><span data-stu-id="29886-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29886-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29886-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="29886-107">からガベージコレクションシステムによって使用されるセグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="29886-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="29886-108">からジェネレーション0の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="29886-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29886-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="29886-109">Remarks</span></span>  
 <span data-ttu-id="29886-110">`SetGCStartupLimits` メソッドは、1回だけ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="29886-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="29886-111">これらの値は後で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="29886-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29886-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="29886-112">Requirements</span></span>  
 <span data-ttu-id="29886-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29886-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29886-114">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="29886-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="29886-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="29886-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29886-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29886-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29886-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="29886-117">See also</span></span>

- [<span data-ttu-id="29886-118">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29886-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
