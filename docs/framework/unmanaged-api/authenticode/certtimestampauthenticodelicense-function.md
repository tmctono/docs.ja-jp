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
ms.openlocfilehash: 5ac7cf92fb9c57491ff45e664513c0e82f22db9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111723"
---
# <a name="certtimestampauthenticodelicense-function"></a><span data-ttu-id="b1874-102">CertTimestampAuthenticodeLicense 関数</span><span class="sxs-lookup"><span data-stu-id="b1874-102">CertTimestampAuthenticodeLicense Function</span></span>
<span data-ttu-id="b1874-103">Authenticode XrML ライセンスにタイム スタンプを付けます。</span><span class="sxs-lookup"><span data-stu-id="b1874-103">Time-stamps an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1874-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1874-104">Syntax</span></span>  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1874-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1874-105">Parameters</span></span>  
 `pSignedLicenseBlob`  
 <span data-ttu-id="b1874-106">[in] タイム スタンプが付けられる、署名付きの Authenticode XrML ライセンス。</span><span class="sxs-lookup"><span data-stu-id="b1874-106">[in] The signed Authenticode XrML license to be time-stamped.</span></span> <span data-ttu-id="b1874-107">参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。</span><span class="sxs-lookup"><span data-stu-id="b1874-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pwszTimestampURI`  
 <span data-ttu-id="b1874-108">[in] タイム スタンプ サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="b1874-108">[in] The time-stamp server's URI.</span></span>  
  
 `pTimestampSignatureBlob`  
 <span data-ttu-id="b1874-109">[out] base64 でエンコードされたタイム スタンプの署名を取得するための、CRYPT_DATA_BLOB へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b1874-109">[out] A pointer to CRYPT_DATA_BLOB to receive the base64-encoded time-stamp signature.</span></span> <span data-ttu-id="b1874-110">解放する呼び出し元の責任`pTimestampSignatureBlob` -> `pbData`で`HepFree()`使用後にします。</span><span class="sxs-lookup"><span data-stu-id="b1874-110">It is the caller's responsibility to free `pTimestampSignatureBlob`->`pbData` with `HepFree()` after use.</span></span> <span data-ttu-id="b1874-111">参照してください、 [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)構造体。</span><span class="sxs-lookup"><span data-stu-id="b1874-111">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1874-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1874-112">Remarks</span></span>  
 <span data-ttu-id="b1874-113">タイム スタンプの署名は、実際は PKCS #7 SignedData メッセージで、この内容は、ライセンスの署名の SignatureValue のバイナリ形式です。</span><span class="sxs-lookup"><span data-stu-id="b1874-113">The time-stamp signature is actually a PKCS #7 SignedData message whose content is the binary form of the SignatureValue from the license's signature.</span></span> <span data-ttu-id="b1874-114">これは基本的に、ライセンスの副署名として機能します。</span><span class="sxs-lookup"><span data-stu-id="b1874-114">Basically, this acts as a counter-signature of the license.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1874-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="b1874-115">Return Value</span></span>  
 `S_OK` <span data-ttu-id="b1874-116">関数が成功するとします。</span><span class="sxs-lookup"><span data-stu-id="b1874-116">if the function succeeds.</span></span> <span data-ttu-id="b1874-117">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b1874-117">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1874-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1874-118">See also</span></span>

- [<span data-ttu-id="b1874-119">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b1874-119">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
