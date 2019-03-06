---
title: ICLRStrongName::StrongNameGetPublicKey メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e66835ec1cdf1327a39223b6cdb187ec47cd7e3d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476309"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="fcbdc-102">ICLRStrongName::StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="fcbdc-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="fcbdc-103">公開/秘密キーのペアから公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="fcbdc-104">暗号化サービス プロバイダー (CSP) 内のキー コンテナー名、またはバイトの生のコレクションとして、キーのペアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcbdc-105">構文</span><span class="sxs-lookup"><span data-stu-id="fcbdc-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcbdc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcbdc-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="fcbdc-107">[in]公開/秘密キー ペアを格納するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="fcbdc-108">場合`pbKeyBlob`が null、 `szKeyContainer` CSP 内の有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="fcbdc-109">ここで、 [iclrstrongname::strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)メソッドは、コンテナーに格納されているキーのペアから公開キーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="fcbdc-110">場合`pbKeyBlob`が null でないと見なされます、キーのペア キー バイナリ ラージ オブジェクト (BLOB) に格納します。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="fcbdc-111">キーは、1024 ビット Rivest-Shamir-Adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="fcbdc-112">この時点でその他の種類のキーがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="fcbdc-113">[in]公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="fcbdc-114">このペアは、Win32 によって作成された形式で、`CryptExportKey`関数。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="fcbdc-115">場合`pbKeyBlob`が null で指定されたキー コンテナー`szKeyContainer`キー ペアを格納すると見なされます。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="fcbdc-116">[in]サイズ (バイト単位) の`pbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="fcbdc-117">[out]返される公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="fcbdc-118">`ppbPublicKeyBlob`パラメーターは、共通言語ランタイムによって割り当てられ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="fcbdc-119">呼び出し元を使用して、メモリを解放する必要があります、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="fcbdc-120">[out]返される公開キー BLOB のサイズ。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcbdc-121">戻り値</span><span class="sxs-lookup"><span data-stu-id="fcbdc-121">Return Value</span></span>  
 <span data-ttu-id="fcbdc-122">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcbdc-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="fcbdc-123">Remarks</span></span>  
 <span data-ttu-id="fcbdc-124">公開キーが含まれている、 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcbdc-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcbdc-125">Requirements</span></span>  
 <span data-ttu-id="fcbdc-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcbdc-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcbdc-127">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fcbdc-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fcbdc-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fcbdc-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcbdc-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcbdc-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbdc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcbdc-130">See also</span></span>
- [<span data-ttu-id="fcbdc-131">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="fcbdc-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="fcbdc-132">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="fcbdc-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="fcbdc-133">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fcbdc-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
