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
ms.openlocfilehash: 4b101a912eb58ed14f81d847ea2fd6ce9f22c065
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787095"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="b8035-102">\_AxlGetIssuerPublicKeyHash 関数</span><span class="sxs-lookup"><span data-stu-id="b8035-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="b8035-103">指定された証明書の署名に使用する秘密キーに関連付けられている公開キーの SHA-1 ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="b8035-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8035-104">構文</span><span class="sxs-lookup"><span data-stu-id="b8035-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8035-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8035-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="b8035-106">[in] CSP 公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="b8035-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="b8035-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8035-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="b8035-108">[out] 16 進エンコードされた公開キー トークンを受け取るための WCHAR \* へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b8035-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8035-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b8035-109">Return Value</span></span>  
 <span data-ttu-id="b8035-110">関数が成功した場合は `S_OK`、それ以外の場合は `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="b8035-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8035-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8035-111">See also</span></span>

- [<span data-ttu-id="b8035-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b8035-112">Authenticode</span></span>](index.md)
