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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142403"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="4e242-102">CertFreeAuthenticodeSignerInfo 関数</span><span class="sxs-lookup"><span data-stu-id="4e242-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="4e242-103">割り当てられているリソース、 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="4e242-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e242-104">構文</span><span class="sxs-lookup"><span data-stu-id="4e242-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e242-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e242-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="4e242-106">[in, out] リリースされる署名者情報。</span><span class="sxs-lookup"><span data-stu-id="4e242-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="4e242-107">参照してください、 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="4e242-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e242-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e242-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="4e242-109">関数が成功するとします。</span><span class="sxs-lookup"><span data-stu-id="4e242-109">if the function succeeds.</span></span> <span data-ttu-id="4e242-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="4e242-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e242-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e242-111">See also</span></span>

- [<span data-ttu-id="4e242-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="4e242-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
