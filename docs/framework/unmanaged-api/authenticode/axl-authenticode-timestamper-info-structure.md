---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dce0e67479418cd8227c75fadd8872a41ae1a799
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741349"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="d61c7-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="d61c7-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="d61c7-103">Authenticode のタイム スタンパー情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="d61c7-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d61c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="d61c7-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d61c7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d61c7-105">Members</span></span>  
  
|<span data-ttu-id="d61c7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d61c7-106">Member</span></span>|<span data-ttu-id="d61c7-107">説明</span><span class="sxs-lookup"><span data-stu-id="d61c7-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="d61c7-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d61c7-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="d61c7-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="d61c7-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="d61c7-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="d61c7-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="d61c7-111">タイム スタンプの時刻。</span><span class="sxs-lookup"><span data-stu-id="d61c7-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="d61c7-112">タイム スタンパーのチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="d61c7-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="d61c7-113">参照してください、 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)構造体。</span><span class="sxs-lookup"><span data-stu-id="d61c7-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d61c7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d61c7-114">See also</span></span>

- [<span data-ttu-id="d61c7-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d61c7-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
