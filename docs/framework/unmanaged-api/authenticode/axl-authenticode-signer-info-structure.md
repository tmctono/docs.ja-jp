---
title: AXL_AUTHENTICODE_SIGNER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 00132bb378d69c0db9fe9d762407707346238917
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132509"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="363d3-102">AXL_AUTHENTICODE_SIGNER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="363d3-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="363d3-103">Authenticode の署名者情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="363d3-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="363d3-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="363d3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="363d3-105">Members</span></span>  
  
|<span data-ttu-id="363d3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="363d3-106">Member</span></span>|<span data-ttu-id="363d3-107">説明</span><span class="sxs-lookup"><span data-stu-id="363d3-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="363d3-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="363d3-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="363d3-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="363d3-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="363d3-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="363d3-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="363d3-111">ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="363d3-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="363d3-112">説明。</span><span class="sxs-lookup"><span data-stu-id="363d3-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="363d3-113">説明の URL。</span><span class="sxs-lookup"><span data-stu-id="363d3-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="363d3-114">署名者のチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="363d3-114">The chain context of the signer.</span></span> <span data-ttu-id="363d3-115">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="363d3-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="363d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="363d3-116">See also</span></span>

- [<span data-ttu-id="363d3-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="363d3-117">Authenticode</span></span>](index.md)
