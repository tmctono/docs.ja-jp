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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cb1f55e1d8643feb2750e8ea468f608dc3d5d40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212064"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="2cc88-102">StrongNameGetPublicKeyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="2cc88-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="2cc88-103">公開/秘密キーのペアから公開キーを取得し、ハッシュ アルゴリズムおよび署名アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cc88-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc88-104">構文</span><span class="sxs-lookup"><span data-stu-id="2cc88-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="2cc88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cc88-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="2cc88-106">[in]公開/秘密キー ペアを格納するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="2cc88-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="2cc88-107">場合`pbKeyBlob`が null、`szKeyContainer`暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cc88-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="2cc88-108">ここで、`StrongNameGetPublicKeyEx`メソッドは、コンテナーに格納されているキーのペアから公開キーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2cc88-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="2cc88-109">場合`pbKeyBlob`が null でないと見なされます、キーのペア キー バイナリ ラージ オブジェクト (BLOB) に格納します。</span><span class="sxs-lookup"><span data-stu-id="2cc88-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="2cc88-110">キーは、1024 ビット Rivest-Shamir-Adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cc88-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="2cc88-111">この時点でその他の種類のキーがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2cc88-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="2cc88-112">[in]公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2cc88-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="2cc88-113">このペアは、Win32 によって作成された形式で、`CryptExportKey`関数。</span><span class="sxs-lookup"><span data-stu-id="2cc88-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="2cc88-114">場合`pbKeyBlob`が null で指定されたキー コンテナー`szKeyContainer`キー ペアを格納すると見なされます。</span><span class="sxs-lookup"><span data-stu-id="2cc88-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="2cc88-115">[in]サイズ (バイト単位) の`pbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="2cc88-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="2cc88-116">[out]返される公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="2cc88-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="2cc88-117">`ppbPublicKeyBlob`パラメーターは、共通言語ランタイムによって割り当てられ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="2cc88-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="2cc88-118">呼び出し元を使用して、メモリを解放する必要があります、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="2cc88-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="2cc88-119">[out]返される公開キー BLOB のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2cc88-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="2cc88-120">[in]アセンブリ ハッシュ アルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="2cc88-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="2cc88-121">指定できる値の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cc88-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="2cc88-122">[in]今後使用するために予約されていますnull を既定値です。</span><span class="sxs-lookup"><span data-stu-id="2cc88-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cc88-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="2cc88-123">Return Value</span></span>  
 <span data-ttu-id="2cc88-124">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="2cc88-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cc88-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cc88-125">Remarks</span></span>  
 <span data-ttu-id="2cc88-126">公開キーが含まれている、 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="2cc88-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cc88-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cc88-127">Remarks</span></span>  
 <span data-ttu-id="2cc88-128">次の表に、許容される値のセット、`uHashAlgId`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2cc88-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="2cc88-129">名前</span><span class="sxs-lookup"><span data-stu-id="2cc88-129">Name</span></span>|<span data-ttu-id="2cc88-130">[値]</span><span class="sxs-lookup"><span data-stu-id="2cc88-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="2cc88-131">なし</span><span class="sxs-lookup"><span data-stu-id="2cc88-131">None</span></span>|<span data-ttu-id="2cc88-132">0</span><span class="sxs-lookup"><span data-stu-id="2cc88-132">0</span></span>|  
|<span data-ttu-id="2cc88-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="2cc88-133">SHA-1</span></span>|<span data-ttu-id="2cc88-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="2cc88-134">0x8004</span></span>|  
|<span data-ttu-id="2cc88-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="2cc88-135">SHA-256</span></span>|<span data-ttu-id="2cc88-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="2cc88-136">0x800c</span></span>|  
|<span data-ttu-id="2cc88-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="2cc88-137">SHA-384</span></span>|<span data-ttu-id="2cc88-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="2cc88-138">0x800d</span></span>|  
|<span data-ttu-id="2cc88-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="2cc88-139">SHA-512</span></span>|<span data-ttu-id="2cc88-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="2cc88-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cc88-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="2cc88-141">Requirements</span></span>  
 <span data-ttu-id="2cc88-142">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cc88-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cc88-143">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2cc88-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2cc88-144">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2cc88-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cc88-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cc88-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc88-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cc88-146">See also</span></span>

- [<span data-ttu-id="2cc88-147">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="2cc88-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="2cc88-148">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="2cc88-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="2cc88-149">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cc88-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="2cc88-150">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="2cc88-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
