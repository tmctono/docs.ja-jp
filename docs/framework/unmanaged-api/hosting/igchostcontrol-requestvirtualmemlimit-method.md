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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948b18832ccfc5e0fc2e42ee58e6444a581de260
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209692"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="532d9-102">IGCHostControl::RequestVirtualMemLimit メソッド</span><span class="sxs-lookup"><span data-stu-id="532d9-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="532d9-103">仮想メモリの制限を変更するホストを要求します。</span><span class="sxs-lookup"><span data-stu-id="532d9-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="532d9-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="532d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="532d9-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="532d9-106">[in]メモリ割り当ての要求されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="532d9-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="532d9-107">[入力、出力]割り当てられたメモリの実際のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="532d9-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532d9-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="532d9-108">Requirements</span></span>  
 <span data-ttu-id="532d9-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="532d9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532d9-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="532d9-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="532d9-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="532d9-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="532d9-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="532d9-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="532d9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="532d9-113">See also</span></span>

- [<span data-ttu-id="532d9-114">IGCHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="532d9-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
