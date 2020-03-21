---
title: StrongNameGetPublicKeyEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176228"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="15f6c-102">StrongNameGetPublicKeyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="15f6c-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="15f6c-103">公開キーと秘密キーのペアから公開キーを取得し、ハッシュ アルゴリズムと署名アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="15f6c-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="15f6c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15f6c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15f6c-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="15f6c-106">[in]公開キーと秘密キーのペアを含むキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="15f6c-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="15f6c-107">null`pbKeyBlob`の場合`szKeyContainer`は、暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15f6c-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="15f6c-108">この場合、メソッドは`StrongNameGetPublicKeyEx`、コンテナーに格納されているキーペアから公開キーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="15f6c-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="15f6c-109">null`pbKeyBlob`でない場合、キー ペアは、キー のバイナリ ラージ オブジェクト (BLOB) に含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="15f6c-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="15f6c-110">キーは、1024 ビットのリベスト シャミール-アドレマン (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="15f6c-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="15f6c-111">現時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="15f6c-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="15f6c-112">[in]公開キーと秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="15f6c-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="15f6c-113">このペアは、Win32`CryptExportKey`関数によって作成された形式です。</span><span class="sxs-lookup"><span data-stu-id="15f6c-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="15f6c-114">null`pbKeyBlob`の場合、指定されたキー`szKeyContainer`コンテナーにはキー ペアが含まれるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="15f6c-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="15f6c-115">[in]のサイズ (バイト単位)`pbKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="15f6c-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="15f6c-116">[アウト]返された公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="15f6c-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="15f6c-117">パラメーター`ppbPublicKeyBlob`は、共通言語ランタイムによって割り当てられ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="15f6c-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="15f6c-118">呼び出し元は、メソッドを使用してメモリ[を](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15f6c-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="15f6c-119">[アウト]返される公開キー BLOB のサイズ。</span><span class="sxs-lookup"><span data-stu-id="15f6c-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="15f6c-120">[in]アセンブリ ハッシュ アルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="15f6c-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="15f6c-121">受け入れられる値の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15f6c-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="15f6c-122">[in]将来の使用のために予約されています。デフォルトは null です。</span><span class="sxs-lookup"><span data-stu-id="15f6c-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15f6c-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="15f6c-123">Return Value</span></span>  
 <span data-ttu-id="15f6c-124">`S_OK`メソッドが正常に完了した場合。それ以外の場合は、失敗を示す HRESULT 値です (リストの[HRESULT の共通値](/windows/win32/seccrypto/common-hresult-values)を参照)。</span><span class="sxs-lookup"><span data-stu-id="15f6c-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f6c-125">解説</span><span class="sxs-lookup"><span data-stu-id="15f6c-125">Remarks</span></span>  
 <span data-ttu-id="15f6c-126">公開キーは[、パブリックキー Blob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)構造体に含まれています。</span><span class="sxs-lookup"><span data-stu-id="15f6c-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f6c-127">解説</span><span class="sxs-lookup"><span data-stu-id="15f6c-127">Remarks</span></span>  
 <span data-ttu-id="15f6c-128">次の表は、パラメーターに使用できる値の`uHashAlgId`セットを示しています。</span><span class="sxs-lookup"><span data-stu-id="15f6c-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="15f6c-129">名前</span><span class="sxs-lookup"><span data-stu-id="15f6c-129">Name</span></span>|<span data-ttu-id="15f6c-130">Value</span><span class="sxs-lookup"><span data-stu-id="15f6c-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="15f6c-131">なし</span><span class="sxs-lookup"><span data-stu-id="15f6c-131">None</span></span>|<span data-ttu-id="15f6c-132">0</span><span class="sxs-lookup"><span data-stu-id="15f6c-132">0</span></span>|  
|<span data-ttu-id="15f6c-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="15f6c-133">SHA-1</span></span>|<span data-ttu-id="15f6c-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="15f6c-134">0x8004</span></span>|  
|<span data-ttu-id="15f6c-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="15f6c-135">SHA-256</span></span>|<span data-ttu-id="15f6c-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="15f6c-136">0x800c</span></span>|  
|<span data-ttu-id="15f6c-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="15f6c-137">SHA-384</span></span>|<span data-ttu-id="15f6c-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="15f6c-138">0x800d</span></span>|  
|<span data-ttu-id="15f6c-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="15f6c-139">SHA-512</span></span>|<span data-ttu-id="15f6c-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="15f6c-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15f6c-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="15f6c-141">Requirements</span></span>  
 <span data-ttu-id="15f6c-142">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15f6c-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f6c-143">**ヘッダー:** メタホスト.h</span><span class="sxs-lookup"><span data-stu-id="15f6c-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15f6c-144">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="15f6c-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15f6c-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f6c-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f6c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="15f6c-146">See also</span></span>

- [<span data-ttu-id="15f6c-147">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="15f6c-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="15f6c-148">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="15f6c-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="15f6c-149">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15f6c-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="15f6c-150">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="15f6c-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
