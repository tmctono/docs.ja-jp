---
title: AXL_AUTHENTICODE_SIGNER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aaa0258b53b6b39874c8c99c71ecf53cbdb8f97
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787081"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="f3a70-102">AXL_AUTHENTICODE_SIGNER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="f3a70-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="f3a70-103">Authenticode の署名者情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="f3a70-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a70-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3a70-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="f3a70-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="f3a70-105">Members</span></span>  
  
|<span data-ttu-id="f3a70-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="f3a70-106">Member</span></span>|<span data-ttu-id="f3a70-107">説明</span><span class="sxs-lookup"><span data-stu-id="f3a70-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="f3a70-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="f3a70-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="f3a70-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="f3a70-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="f3a70-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="f3a70-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="f3a70-111">ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="f3a70-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="f3a70-112">説明。</span><span class="sxs-lookup"><span data-stu-id="f3a70-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="f3a70-113">説明の URL。</span><span class="sxs-lookup"><span data-stu-id="f3a70-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="f3a70-114">署名者のチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="f3a70-114">The chain context of the signer.</span></span> <span data-ttu-id="f3a70-115">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3a70-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3a70-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3a70-116">See also</span></span>

- [<span data-ttu-id="f3a70-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f3a70-117">Authenticode</span></span>](index.md)
