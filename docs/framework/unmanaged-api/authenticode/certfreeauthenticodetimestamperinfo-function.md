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
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786994"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="45eb9-102">CertFreeAuthenticodeTimestamperInfo 関数</span><span class="sxs-lookup"><span data-stu-id="45eb9-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="45eb9-103">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)構造体に割り当てられたリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="45eb9-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45eb9-104">構文</span><span class="sxs-lookup"><span data-stu-id="45eb9-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45eb9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45eb9-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="45eb9-106">[入力、出力] 解放されるタイム スタンパー情報。</span><span class="sxs-lookup"><span data-stu-id="45eb9-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="45eb9-107">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45eb9-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45eb9-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="45eb9-108">Return Value</span></span>  
 <span data-ttu-id="45eb9-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="45eb9-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="45eb9-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="45eb9-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45eb9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="45eb9-111">See also</span></span>

- [<span data-ttu-id="45eb9-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="45eb9-112">Authenticode</span></span>](index.md)
