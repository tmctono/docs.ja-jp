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
ms.openlocfilehash: 1f53df33a65d3f75b7574eda3507e370c2e086ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099817"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="1ff1f-102">\_AxlRSAKeyValueToPublicKeyToken 関数</span><span class="sxs-lookup"><span data-stu-id="1ff1f-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="1ff1f-103">Modulus および Exponent を、厳密な名前の公開キー トークンに変換します。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff1f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ff1f-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ff1f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ff1f-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="1ff1f-106">からBase64 でエンコードされた剰余 blob (\<剰余 > 要素)。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="1ff1f-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="1ff1f-108">からBase64 でエンコードされた指数 (\<指数部の > 要素)。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="1ff1f-109">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="1ff1f-110">[out] 16 進エンコードされた公開キー トークンを受け取るための WCHAR \* へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ff1f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="1ff1f-111">Return Value</span></span>  
 <span data-ttu-id="1ff1f-112">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="1ff1f-113">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="1ff1f-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff1f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ff1f-114">See also</span></span>

- [<span data-ttu-id="1ff1f-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1ff1f-115">Authenticode</span></span>](index.md)
