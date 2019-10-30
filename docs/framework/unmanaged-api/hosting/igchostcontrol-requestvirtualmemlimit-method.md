---
title: IGCHostControl::RequestVirtualMemLimit メソッド
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: ccff575974093de0bf00b257cba78c509f9cbd92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134774"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="e8882-102">IGCHostControl::RequestVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="e8882-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="e8882-103">仮想メモリの制限を変更するようにホストに要求します。</span><span class="sxs-lookup"><span data-stu-id="e8882-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8882-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8882-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8882-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8882-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="e8882-106">から割り当てられるメモリの要求サイズ。</span><span class="sxs-lookup"><span data-stu-id="e8882-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="e8882-107">[入力、出力]割り当てられたメモリの実際のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8882-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8882-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="e8882-108">Requirements</span></span>  
 <span data-ttu-id="e8882-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8882-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8882-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e8882-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8882-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e8882-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8882-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8882-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8882-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8882-113">See also</span></span>

- [<span data-ttu-id="e8882-114">IGCHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e8882-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
