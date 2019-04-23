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
ms.openlocfilehash: bdb764417b757cd7388c49d7e5cac9a960074820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142403"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="e22f6-102">CertFreeAuthenticodeSignerInfo 関数</span><span class="sxs-lookup"><span data-stu-id="e22f6-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="e22f6-103">割り当てられているリソース、 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="e22f6-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e22f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="e22f6-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e22f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e22f6-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="e22f6-106">[in, out] リリースされる署名者情報。</span><span class="sxs-lookup"><span data-stu-id="e22f6-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="e22f6-107">参照してください、 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="e22f6-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e22f6-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e22f6-108">Return Value</span></span>  
 <span data-ttu-id="e22f6-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="e22f6-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e22f6-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="e22f6-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22f6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e22f6-111">See also</span></span>

- [<span data-ttu-id="e22f6-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e22f6-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
