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
ms.openlocfilehash: 448712561f1531a055ac141db9825581525c779c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948938"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="85b71-102">_AxlGetIssuerPublicKeyHash 関数</span><span class="sxs-lookup"><span data-stu-id="85b71-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="85b71-103">指定された証明書の署名に使用する秘密キーに関連付けられている公開キーの SHA-1 ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="85b71-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b71-104">構文</span><span class="sxs-lookup"><span data-stu-id="85b71-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85b71-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85b71-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="85b71-106">[in] CSP 公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="85b71-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="85b71-107">参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。</span><span class="sxs-lookup"><span data-stu-id="85b71-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="85b71-108">[out] 16 進エンコードされた公開キー トークンを受け取るための WCHAR \* へのポインター。</span><span class="sxs-lookup"><span data-stu-id="85b71-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85b71-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="85b71-109">Return Value</span></span>  
 <span data-ttu-id="85b71-110">関数が成功した場合は `S_OK`、それ以外の場合は `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="85b71-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b71-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="85b71-111">See also</span></span>

- [<span data-ttu-id="85b71-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="85b71-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
