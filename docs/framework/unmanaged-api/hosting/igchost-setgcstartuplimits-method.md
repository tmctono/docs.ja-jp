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
ms.openlocfilehash: 87ba947b9564f82f8daf8cd2ba0acac5cc3587ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928675"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="c03f9-102">IGCHost::SetGCStartupLimits メソッド</span><span class="sxs-lookup"><span data-stu-id="c03f9-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="c03f9-103">ジェネレーション0のセグメントサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="c03f9-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c03f9-104">.NET Framework 4.5 以降では、 [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)メソッドを使用して、セグメントサイズと最大`DWORD`ジェネレーション0のサイズをより大きい値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c03f9-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c03f9-105">構文</span><span class="sxs-lookup"><span data-stu-id="c03f9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c03f9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c03f9-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="c03f9-107">からガベージコレクションシステムによって使用されるセグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c03f9-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="c03f9-108">からジェネレーション0の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c03f9-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c03f9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c03f9-109">Remarks</span></span>  
 <span data-ttu-id="c03f9-110">メソッド`SetGCStartupLimits`を呼び出すことができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="c03f9-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="c03f9-111">これらの値は後で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c03f9-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c03f9-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c03f9-112">Requirements</span></span>  
 <span data-ttu-id="c03f9-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c03f9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c03f9-114">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="c03f9-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c03f9-115">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c03f9-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c03f9-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c03f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c03f9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c03f9-117">See also</span></span>

- [<span data-ttu-id="c03f9-118">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c03f9-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
