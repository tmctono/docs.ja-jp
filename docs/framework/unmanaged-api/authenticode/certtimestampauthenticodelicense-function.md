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
ms.openlocfilehash: aaf76d4c3d0f5fb59aeb35fae7a7020ee97b74d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776478"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="b6cc9-102">CertTimestampAuthenticodeLicense 関数</span><span class="sxs-lookup"><span data-stu-id="b6cc9-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="b6cc9-103">Authenticode XrML ライセンスにタイム スタンプを付けます。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6cc9-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6cc9-104">Syntax</span></span>  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6cc9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6cc9-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="b6cc9-106">[in] タイム スタンプが付けられる、署名付きの Authenticode XrML ライセンス。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="b6cc9-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="b6cc9-108">[in] タイム スタンプ サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="b6cc9-109">[out] base64 でエンコードされたタイム スタンプの署名を取得するための、CRYPT_DATA_BLOB へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="b6cc9-110">呼び出し元は、使用後にを`pTimestampSignatureBlob` `HepFree()`解放-> `pbData`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="b6cc9-111">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-111">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6cc9-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6cc9-112">Remarks</span></span>  
 <span data-ttu-id="b6cc9-113">タイム スタンプの署名は、実際は PKCS #7 SignedData メッセージで、この内容は、ライセンスの署名の SignatureValue のバイナリ形式です。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="b6cc9-114">これは基本的に、ライセンスの副署名として機能します。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6cc9-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="b6cc9-115">Return Value</span></span>  
 <span data-ttu-id="b6cc9-116">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-116">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b6cc9-117">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b6cc9-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cc9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6cc9-118">See also</span></span>

- [<span data-ttu-id="b6cc9-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b6cc9-119">Authenticode</span></span>](index.md)
