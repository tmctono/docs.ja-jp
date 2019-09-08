---
title: _AxlRSAKeyValueToPublicKeyToken 関数
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690035ffe0724d3987a198c78bf14e668527b98a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787028"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="92ca9-102">\_AxlRSAKeyValueToPublicKeyToken 関数</span><span class="sxs-lookup"><span data-stu-id="92ca9-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="92ca9-103">Modulus および Exponent を、厳密な名前の公開キー トークンに変換します。</span><span class="sxs-lookup"><span data-stu-id="92ca9-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ca9-104">構文</span><span class="sxs-lookup"><span data-stu-id="92ca9-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ca9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92ca9-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="92ca9-106">からBase64 でエンコードされた剰余 blob ( \<剰余 > 要素から)。</span><span class="sxs-lookup"><span data-stu-id="92ca9-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="92ca9-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ca9-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="92ca9-108">からBase64 でエンコードされた指数 ( \<指数 > 要素)。</span><span class="sxs-lookup"><span data-stu-id="92ca9-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="92ca9-109">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ca9-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="92ca9-110">[out] 16 進エンコードされた公開キー トークンを受け取るための WCHAR \* へのポインター。</span><span class="sxs-lookup"><span data-stu-id="92ca9-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92ca9-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="92ca9-111">Return Value</span></span>  
 <span data-ttu-id="92ca9-112">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="92ca9-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="92ca9-113">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="92ca9-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ca9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="92ca9-114">See also</span></span>

- [<span data-ttu-id="92ca9-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="92ca9-115">Authenticode</span></span>](index.md)
