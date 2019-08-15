---
title: CertTimestampAuthenticodeLicense 関数
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c2bb6f0324c461f59bd98a70333b176e79a16a6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039592"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="cea28-102">CertTimestampAuthenticodeLicense 関数</span><span class="sxs-lookup"><span data-stu-id="cea28-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="cea28-103">Authenticode XrML ライセンスにタイム スタンプを付けます。</span><span class="sxs-lookup"><span data-stu-id="cea28-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea28-104">構文</span><span class="sxs-lookup"><span data-stu-id="cea28-104">Syntax</span></span>  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cea28-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cea28-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="cea28-106">[in] タイム スタンプが付けられる、署名付きの Authenticode XrML ライセンス。</span><span class="sxs-lookup"><span data-stu-id="cea28-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="cea28-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea28-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="cea28-108">[in] タイム スタンプ サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="cea28-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="cea28-109">[out] base64 でエンコードされたタイム スタンプの署名を取得するための、CRYPT_DATA_BLOB へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cea28-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="cea28-110">呼び出し元は、使用後にを`pTimestampSignatureBlob` `HepFree()`解放-> `pbData`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cea28-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="cea28-111">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea28-111">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cea28-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="cea28-112">Remarks</span></span>  
 <span data-ttu-id="cea28-113">タイム スタンプの署名は、実際は PKCS #7 SignedData メッセージで、この内容は、ライセンスの署名の SignatureValue のバイナリ形式です。</span><span class="sxs-lookup"><span data-stu-id="cea28-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="cea28-114">これは基本的に、ライセンスの副署名として機能します。</span><span class="sxs-lookup"><span data-stu-id="cea28-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cea28-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="cea28-115">Return Value</span></span>  
 <span data-ttu-id="cea28-116">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="cea28-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="cea28-117">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="cea28-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea28-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cea28-118">See also</span></span>

- [<span data-ttu-id="cea28-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="cea28-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
