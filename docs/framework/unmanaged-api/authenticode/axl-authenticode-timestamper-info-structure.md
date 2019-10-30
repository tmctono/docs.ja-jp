---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: 036397928703aea6199a59ae9c1e66153c30ec7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132501"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="83e94-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="83e94-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="83e94-103">Authenticode のタイム スタンパー情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="83e94-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e94-104">構文</span><span class="sxs-lookup"><span data-stu-id="83e94-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="83e94-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="83e94-105">Members</span></span>  
  
|<span data-ttu-id="83e94-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="83e94-106">Member</span></span>|<span data-ttu-id="83e94-107">説明</span><span class="sxs-lookup"><span data-stu-id="83e94-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="83e94-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="83e94-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="83e94-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="83e94-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="83e94-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="83e94-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="83e94-111">タイム スタンプの時刻。</span><span class="sxs-lookup"><span data-stu-id="83e94-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="83e94-112">タイム スタンパーのチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="83e94-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="83e94-113">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e94-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83e94-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="83e94-114">See also</span></span>

- [<span data-ttu-id="83e94-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="83e94-115">Authenticode</span></span>](index.md)
