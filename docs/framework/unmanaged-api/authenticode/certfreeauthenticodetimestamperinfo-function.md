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
ms.openlocfilehash: 680d9c959c57620ff38f8e785c670b451e5805b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741222"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="2879f-102">CertFreeAuthenticodeTimestamperInfo 関数</span><span class="sxs-lookup"><span data-stu-id="2879f-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="2879f-103">割り当てられているリソース、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="2879f-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2879f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2879f-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2879f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2879f-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="2879f-106">[入力、出力] 解放されるタイム スタンパー情報。</span><span class="sxs-lookup"><span data-stu-id="2879f-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="2879f-107">参照してください、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="2879f-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2879f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2879f-108">Return Value</span></span>  
 <span data-ttu-id="2879f-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="2879f-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="2879f-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="2879f-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2879f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="2879f-111">See also</span></span>

- [<span data-ttu-id="2879f-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2879f-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
