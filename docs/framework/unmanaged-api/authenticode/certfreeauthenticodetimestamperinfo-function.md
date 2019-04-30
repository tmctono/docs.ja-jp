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
ms.openlocfilehash: 355e6c7b1cd77936d5ccfa5ccff7312c8e35ac63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941648"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="e84cb-102">CertFreeAuthenticodeTimestamperInfo 関数</span><span class="sxs-lookup"><span data-stu-id="e84cb-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="e84cb-103">割り当てられているリソース、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="e84cb-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e84cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="e84cb-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e84cb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e84cb-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="e84cb-106">[入力、出力] 解放されるタイム スタンパー情報。</span><span class="sxs-lookup"><span data-stu-id="e84cb-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="e84cb-107">参照してください、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="e84cb-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e84cb-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e84cb-108">Return Value</span></span>  
 <span data-ttu-id="e84cb-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="e84cb-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e84cb-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="e84cb-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84cb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e84cb-111">See also</span></span>

- [<span data-ttu-id="e84cb-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e84cb-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
