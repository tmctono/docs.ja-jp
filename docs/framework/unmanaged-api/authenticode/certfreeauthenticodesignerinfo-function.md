---
title: CertFreeAuthenticodeSignerInfo 関数
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42f5685a9a976be7a3a73badf286f77216e43106
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741245"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="06540-102">CertFreeAuthenticodeSignerInfo 関数</span><span class="sxs-lookup"><span data-stu-id="06540-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="06540-103">割り当てられているリソース、 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="06540-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06540-104">構文</span><span class="sxs-lookup"><span data-stu-id="06540-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06540-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06540-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="06540-106">[in, out] リリースされる署名者情報。</span><span class="sxs-lookup"><span data-stu-id="06540-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="06540-107">参照してください、 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="06540-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06540-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="06540-108">Return Value</span></span>  
 <span data-ttu-id="06540-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="06540-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="06540-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="06540-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06540-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="06540-111">See also</span></span>

- [<span data-ttu-id="06540-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="06540-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
