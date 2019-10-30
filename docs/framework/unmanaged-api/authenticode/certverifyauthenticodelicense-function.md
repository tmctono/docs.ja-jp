---
title: CertVerifyAuthenticodeLicense 関数
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
ms.openlocfilehash: 7cd25a24533b04dc45ee734f9e9639391311405a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099744"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="00bf6-102">CertVerifyAuthenticodeLicense 関数</span><span class="sxs-lookup"><span data-stu-id="00bf6-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="00bf6-103">Authenticode XrML ライセンスの有効性を検証します。</span><span class="sxs-lookup"><span data-stu-id="00bf6-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00bf6-104">構文</span><span class="sxs-lookup"><span data-stu-id="00bf6-104">Syntax</span></span>  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00bf6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00bf6-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="00bf6-106">[in] 検証する Authenticode XrML ライセンス。</span><span class="sxs-lookup"><span data-stu-id="00bf6-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="00bf6-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00bf6-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="00bf6-108">[in] オプション。</span><span class="sxs-lookup"><span data-stu-id="00bf6-108">[in] Optional.</span></span> <span data-ttu-id="00bf6-109">以下の値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="00bf6-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="00bf6-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="00bf6-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="00bf6-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="00bf6-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="00bf6-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="00bf6-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="00bf6-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="00bf6-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="00bf6-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="00bf6-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="00bf6-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="00bf6-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="00bf6-116">[out] 署名者の情報を受け取るため。</span><span class="sxs-lookup"><span data-stu-id="00bf6-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="00bf6-117">ライセンスに署名がない場合、`dwError` は TRUST_E_NOSIGNATURE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="00bf6-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="00bf6-118">使用後に、 [Certfree認証 Oデザイナ情報](certfreeauthenticodesignerinfo-function.md)関数を使用してリソースを解放するのは、呼び出し元の責任です。</span><span class="sxs-lookup"><span data-stu-id="00bf6-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="00bf6-119">「 [AXL_AUTHENTICODE_SIGNER_INFO 構造体](axl-authenticode-signer-info-structure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00bf6-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="00bf6-120">[out] 可能な場合は、タイム スタンプの情報を受け取るため。</span><span class="sxs-lookup"><span data-stu-id="00bf6-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="00bf6-121">ライセンスにタイム スタンプがない場合、`dwError` は TRUST_E_NOSIGNATURE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="00bf6-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="00bf6-122">使用後に[CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md)関数を使用してリソースを解放するのは、呼び出し元の責任です。</span><span class="sxs-lookup"><span data-stu-id="00bf6-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="00bf6-123">「 [AXL_AUTHENTICODE_TIMESTAMPER_INFO 構造体](axl-authenticode-timestamper-info-structure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00bf6-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00bf6-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="00bf6-124">Return Value</span></span>  
 <span data-ttu-id="00bf6-125">正常に終了した場合は `S_OK` を返します。</span><span class="sxs-lookup"><span data-stu-id="00bf6-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="00bf6-126">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="00bf6-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00bf6-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="00bf6-127">See also</span></span>

- [<span data-ttu-id="00bf6-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="00bf6-128">Authenticode</span></span>](index.md)
- [<span data-ttu-id="00bf6-129">GetHashFromHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="00bf6-129">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="00bf6-130">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bf6-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
