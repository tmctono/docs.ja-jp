---
title: CertFreeAuthenticodeTimestamperInfo 関数
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 082ed24eb65de12f337ab4a379b088da0f6eea5a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497380"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="60efe-102">CertFreeAuthenticodeTimestamperInfo 関数</span><span class="sxs-lookup"><span data-stu-id="60efe-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="60efe-103">割り当てられているリソース、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="60efe-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60efe-104">構文</span><span class="sxs-lookup"><span data-stu-id="60efe-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60efe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60efe-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="60efe-106">[入力、出力] 解放されるタイム スタンパー情報。</span><span class="sxs-lookup"><span data-stu-id="60efe-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="60efe-107">参照してください、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="60efe-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60efe-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="60efe-108">Return Value</span></span>  
 <span data-ttu-id="60efe-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="60efe-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="60efe-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="60efe-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60efe-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="60efe-111">See also</span></span>
- [<span data-ttu-id="60efe-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="60efe-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
