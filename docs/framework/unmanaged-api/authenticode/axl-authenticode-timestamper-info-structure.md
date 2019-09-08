---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae7879e1f6598108d839287792ed441391764ae2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776648"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="99155-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="99155-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="99155-103">Authenticode のタイム スタンパー情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="99155-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99155-104">構文</span><span class="sxs-lookup"><span data-stu-id="99155-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="99155-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="99155-105">Members</span></span>  
  
|<span data-ttu-id="99155-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="99155-106">Member</span></span>|<span data-ttu-id="99155-107">説明</span><span class="sxs-lookup"><span data-stu-id="99155-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="99155-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="99155-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="99155-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="99155-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="99155-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="99155-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="99155-111">タイム スタンプの時刻。</span><span class="sxs-lookup"><span data-stu-id="99155-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="99155-112">タイム スタンパーのチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="99155-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="99155-113">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99155-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99155-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="99155-114">See also</span></span>

- [<span data-ttu-id="99155-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="99155-115">Authenticode</span></span>](index.md)
