---
title: _AxlGetIssuerPublicKeyHash 関数
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de55594db68e084009a095a083e065fbd0b8f0df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741335"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="d3953-102">\_AxlGetIssuerPublicKeyHash 関数</span><span class="sxs-lookup"><span data-stu-id="d3953-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="d3953-103">指定された証明書の署名に使用する秘密キーに関連付けられている公開キーの SHA-1 ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3953-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3953-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3953-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3953-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3953-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="d3953-106">[in] CSP 公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="d3953-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="d3953-107">参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。</span><span class="sxs-lookup"><span data-stu-id="d3953-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="d3953-108">[out] 16 進エンコードされた公開キー トークンを受け取るための WCHAR \* へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3953-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3953-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d3953-109">Return Value</span></span>  
 <span data-ttu-id="d3953-110">関数が成功した場合は `S_OK`、それ以外の場合は `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="d3953-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3953-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3953-111">See also</span></span>

- [<span data-ttu-id="d3953-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d3953-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
