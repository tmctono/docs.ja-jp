---
title: IGCHost::SetVirtualMemLimit メソッド
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: c060e4883335a8318970b5fbd74bf72c9e13f5bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134860"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="5645e-102">IGCHost::SetVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="5645e-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="5645e-103">ランタイムの仮想メモリの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="5645e-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5645e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5645e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5645e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5645e-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="5645e-106">からランタイムの仮想メモリの最大サイズ (mb 単位)。</span><span class="sxs-lookup"><span data-stu-id="5645e-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5645e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5645e-107">Remarks</span></span>  
 <span data-ttu-id="5645e-108">ランタイムの仮想メモリの最大サイズは動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="5645e-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5645e-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="5645e-109">Requirements</span></span>  
 <span data-ttu-id="5645e-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5645e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5645e-111">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="5645e-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5645e-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5645e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5645e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5645e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5645e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5645e-114">See also</span></span>

- [<span data-ttu-id="5645e-115">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5645e-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
