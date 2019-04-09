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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5e90055a08227ea7cb7fa1b459fe6f5f3a81fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127336"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="c2e76-102">IGCHost2::SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="c2e76-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="c2e76-103">ジェネレーション 0 のセグメントのサイズと最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2e76-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e76-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2e76-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2e76-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2e76-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="c2e76-106">[in]ガベージ コレクション システムによって使用されるセグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c2e76-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="c2e76-107">[in]ジェネレーション 0 の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c2e76-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2e76-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2e76-108">Remarks</span></span>  
 <span data-ttu-id="c2e76-109">値を`SetGCStartupLimitsEx`ホストを開始する前に、セットを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c2e76-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="c2e76-110">これらの値は、後で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2e76-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e76-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2e76-111">Requirements</span></span>  
 <span data-ttu-id="c2e76-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2e76-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e76-113">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="c2e76-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c2e76-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c2e76-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c2e76-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c2e76-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2e76-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2e76-116">See also</span></span>

- [<span data-ttu-id="c2e76-117">IGCHost2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2e76-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
