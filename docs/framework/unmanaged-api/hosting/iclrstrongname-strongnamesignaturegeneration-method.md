---
title: ICLRStrongName::StrongNameSignatureGeneration メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178050"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="66754-102">ICLRStrongName::StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="66754-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="66754-103">指定したアセンブリに対して厳密な名前の署名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="66754-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66754-104">構文</span><span class="sxs-lookup"><span data-stu-id="66754-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66754-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66754-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="66754-106">[in]厳密な名前の署名が生成されるアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66754-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="66754-107">[in]公開キーと秘密キーのペアを含むキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="66754-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="66754-108">null`pbKeyBlob`の場合`wszKeyContainer`は、暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66754-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="66754-109">この場合、コンテナーに格納されているキーペアを使用してファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="66754-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="66754-110">null`pbKeyBlob`でない場合、キー ペアは、キー のバイナリ ラージ オブジェクト (BLOB) に含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="66754-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="66754-111">キーは、1024 ビットのリベスト シャミール-アドレマン (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="66754-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="66754-112">現時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="66754-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="66754-113">[in]公開キーと秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="66754-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="66754-114">このペアは、Win32`CryptExportKey`関数によって作成された形式です。</span><span class="sxs-lookup"><span data-stu-id="66754-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="66754-115">null`pbKeyBlob`の場合、指定されたキー`wszKeyContainer`コンテナーにはキー ペアが含まれるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="66754-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="66754-116">[in]のサイズ (バイト単位)`pbKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="66754-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="66754-117">[アウト]共通言語ランタイムが署名を返す場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="66754-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="66754-118">null`ppbSignatureBlob`の場合、ランタイムは、 で指定されたファイルに`wszFilePath`署名を格納します。</span><span class="sxs-lookup"><span data-stu-id="66754-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="66754-119">null`ppbSignatureBlob`でない場合、共通言語ランタイムは、署名を返す領域を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="66754-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="66754-120">呼び出し元は、メソッドを使用してこの領域[を解放](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66754-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="66754-121">[アウト]返されたシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="66754-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66754-122">戻り値</span><span class="sxs-lookup"><span data-stu-id="66754-122">Return Value</span></span>  
 <span data-ttu-id="66754-123">`S_OK`メソッドが正常に完了した場合。それ以外の場合は、失敗を示す HRESULT 値です (リストの[HRESULT の共通値](/windows/win32/seccrypto/common-hresult-values)を参照)。</span><span class="sxs-lookup"><span data-stu-id="66754-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66754-124">解説</span><span class="sxs-lookup"><span data-stu-id="66754-124">Remarks</span></span>  
 <span data-ttu-id="66754-125">署名を`wszFilePath`作成せずに署名のサイズを計算するには、 に null を指定します。</span><span class="sxs-lookup"><span data-stu-id="66754-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="66754-126">署名は、ファイルに直接格納するか、または呼び出し元に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="66754-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66754-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="66754-127">Requirements</span></span>  
 <span data-ttu-id="66754-128">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66754-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66754-129">**ヘッダー:** メタホスト.h</span><span class="sxs-lookup"><span data-stu-id="66754-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="66754-130">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="66754-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66754-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66754-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66754-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="66754-132">See also</span></span>

- [<span data-ttu-id="66754-133">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="66754-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="66754-134">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66754-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
