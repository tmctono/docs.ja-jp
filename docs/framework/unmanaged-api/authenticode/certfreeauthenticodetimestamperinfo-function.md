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
ms.openlocfilehash: 4f0806e0273b111e3398fb8f2884231b96cf1116
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099771"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="5c0c4-102">CertFreeAuthenticodeTimestamperInfo 関数</span><span class="sxs-lookup"><span data-stu-id="5c0c4-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="5c0c4-103">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)構造体に割り当てられたリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="5c0c4-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c0c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c0c4-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c0c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c0c4-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="5c0c4-106">[入力、出力] 解放されるタイム スタンパー情報。</span><span class="sxs-lookup"><span data-stu-id="5c0c4-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="5c0c4-107">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c0c4-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c0c4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5c0c4-108">Return Value</span></span>  
 <span data-ttu-id="5c0c4-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="5c0c4-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="5c0c4-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="5c0c4-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0c4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c0c4-111">See also</span></span>

- [<span data-ttu-id="5c0c4-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="5c0c4-112">Authenticode</span></span>](index.md)
