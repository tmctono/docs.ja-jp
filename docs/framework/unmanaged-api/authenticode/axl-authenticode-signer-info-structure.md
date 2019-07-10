---
title: AXL_AUTHENTICODE_SIGNER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 232c78db32aecd0ee1379d4d969fa0378db4159a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741355"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="0fb35-102">AXL_AUTHENTICODE_SIGNER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="0fb35-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="0fb35-103">Authenticode の署名者情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="0fb35-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb35-104">構文</span><span class="sxs-lookup"><span data-stu-id="0fb35-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0fb35-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="0fb35-105">Members</span></span>  
  
|<span data-ttu-id="0fb35-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="0fb35-106">Member</span></span>|<span data-ttu-id="0fb35-107">説明</span><span class="sxs-lookup"><span data-stu-id="0fb35-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="0fb35-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="0fb35-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="0fb35-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="0fb35-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="0fb35-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="0fb35-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="0fb35-111">ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="0fb35-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="0fb35-112">説明。</span><span class="sxs-lookup"><span data-stu-id="0fb35-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="0fb35-113">説明の URL。</span><span class="sxs-lookup"><span data-stu-id="0fb35-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="0fb35-114">署名者のチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="0fb35-114">The chain context of the signer.</span></span> <span data-ttu-id="0fb35-115">参照してください、 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)構造体。</span><span class="sxs-lookup"><span data-stu-id="0fb35-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fb35-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fb35-116">See also</span></span>

- [<span data-ttu-id="0fb35-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="0fb35-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
