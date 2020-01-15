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
ms.openlocfilehash: 834292192aa447a113372bc8807041954b39a115
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937768"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="b54f6-102">StrongNameGetPublicKeyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="b54f6-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="b54f6-103">公開キーと秘密キーのペアから公開キーを取得し、ハッシュアルゴリズムと署名アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="b54f6-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="b54f6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b54f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b54f6-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="b54f6-106">から公開キーと秘密キーのペアを格納するキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="b54f6-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="b54f6-107">`pbKeyBlob` が null の場合、`szKeyContainer` は暗号化サービスプロバイダー (CSP) 内の有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54f6-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="b54f6-108">この場合、`StrongNameGetPublicKeyEx` メソッドは、コンテナーに格納されているキーペアから公開キーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="b54f6-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="b54f6-109">`pbKeyBlob` が null でない場合、キーのペアは、バイナリラージオブジェクト (BLOB) に格納されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="b54f6-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="b54f6-110">キーは 1024-Rivest-shamir-adleman-Rivest-shamir-adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54f6-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="b54f6-111">この時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b54f6-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b54f6-112">から公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b54f6-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="b54f6-113">このペアは、Win32 `CryptExportKey` 関数によって作成される形式です。</span><span class="sxs-lookup"><span data-stu-id="b54f6-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="b54f6-114">`pbKeyBlob` が null の場合、`szKeyContainer` によって指定されたキーコンテナーには、キーのペアが含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="b54f6-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b54f6-115">から`pbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b54f6-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="b54f6-116">入出力返された公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="b54f6-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="b54f6-117">`ppbPublicKeyBlob` パラメーターは、共通言語ランタイムによって割り当てられ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="b54f6-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="b54f6-118">呼び出し元は、 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッドを使用して、メモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54f6-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="b54f6-119">入出力返される公開キー BLOB のサイズ。</span><span class="sxs-lookup"><span data-stu-id="b54f6-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="b54f6-120">からアセンブリハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="b54f6-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="b54f6-121">許容される値の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b54f6-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="b54f6-122">から将来使用するために予約されています。既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="b54f6-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b54f6-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="b54f6-123">Return Value</span></span>  
 <span data-ttu-id="b54f6-124">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b54f6-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b54f6-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="b54f6-125">Remarks</span></span>  
 <span data-ttu-id="b54f6-126">公開キーは[Publickeyblob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)構造に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b54f6-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b54f6-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="b54f6-127">Remarks</span></span>  
 <span data-ttu-id="b54f6-128">次の表は、`uHashAlgId` パラメーターで許容される値のセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="b54f6-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="b54f6-129">[名前]</span><span class="sxs-lookup"><span data-stu-id="b54f6-129">Name</span></span>|<span data-ttu-id="b54f6-130">Value</span><span class="sxs-lookup"><span data-stu-id="b54f6-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b54f6-131">[なし]</span><span class="sxs-lookup"><span data-stu-id="b54f6-131">None</span></span>|<span data-ttu-id="b54f6-132">0</span><span class="sxs-lookup"><span data-stu-id="b54f6-132">0</span></span>|  
|<span data-ttu-id="b54f6-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="b54f6-133">SHA-1</span></span>|<span data-ttu-id="b54f6-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="b54f6-134">0x8004</span></span>|  
|<span data-ttu-id="b54f6-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="b54f6-135">SHA-256</span></span>|<span data-ttu-id="b54f6-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="b54f6-136">0x800c</span></span>|  
|<span data-ttu-id="b54f6-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="b54f6-137">SHA-384</span></span>|<span data-ttu-id="b54f6-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="b54f6-138">0x800d</span></span>|  
|<span data-ttu-id="b54f6-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="b54f6-139">SHA-512</span></span>|<span data-ttu-id="b54f6-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="b54f6-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b54f6-141">要件</span><span class="sxs-lookup"><span data-stu-id="b54f6-141">Requirements</span></span>  
 <span data-ttu-id="b54f6-142">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b54f6-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b54f6-143">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="b54f6-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b54f6-144">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b54f6-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b54f6-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b54f6-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54f6-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="b54f6-146">See also</span></span>

- [<span data-ttu-id="b54f6-147">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="b54f6-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="b54f6-148">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="b54f6-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="b54f6-149">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b54f6-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="b54f6-150">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="b54f6-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
