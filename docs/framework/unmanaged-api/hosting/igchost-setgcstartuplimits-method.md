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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e65a83d1da0580436babd15e4f27e2db7a698668
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377611"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="ac91c-102">IGCHost::SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="ac91c-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="ac91c-103">ジェネレーション 0 のセグメントのサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="ac91c-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac91c-104">以降、.NET Framework 4.5 に設定できますセグメントのサイズと最大のジェネレーション 0 のサイズの値より大きい`DWORD`を使用して、 [igchost 2::setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ac91c-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac91c-105">構文</span><span class="sxs-lookup"><span data-stu-id="ac91c-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac91c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac91c-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="ac91c-107">[in]ガベージ コレクション システムによって使用されるセグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="ac91c-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="ac91c-108">[in]ジェネレーション 0 の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="ac91c-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac91c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac91c-109">Remarks</span></span>  
 <span data-ttu-id="ac91c-110">`SetGCStartupLimits`メソッドを 1 回だけ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac91c-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="ac91c-111">これらの値は、後で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac91c-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac91c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ac91c-112">Requirements</span></span>  
 <span data-ttu-id="ac91c-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac91c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac91c-114">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="ac91c-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ac91c-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ac91c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac91c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac91c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac91c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac91c-117">See also</span></span>

- [<span data-ttu-id="ac91c-118">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac91c-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
