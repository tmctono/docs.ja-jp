---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d82ed3299f967457fe967d096a238da6143751a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219162"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="c6446-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="c6446-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="c6446-103">Authenticode のタイム スタンパー情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="c6446-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6446-104">構文</span><span class="sxs-lookup"><span data-stu-id="c6446-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c6446-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6446-105">Members</span></span>  
  
|<span data-ttu-id="c6446-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6446-106">Member</span></span>|<span data-ttu-id="c6446-107">説明</span><span class="sxs-lookup"><span data-stu-id="c6446-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="c6446-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c6446-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="c6446-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="c6446-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="c6446-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="c6446-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="c6446-111">タイム スタンプの時刻。</span><span class="sxs-lookup"><span data-stu-id="c6446-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="c6446-112">タイム スタンパーのチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="c6446-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="c6446-113">参照してください、 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)構造体。</span><span class="sxs-lookup"><span data-stu-id="c6446-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6446-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6446-114">See also</span></span>

- [<span data-ttu-id="c6446-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c6446-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
