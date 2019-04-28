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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663789"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="bdcb2-102">ICLRStrongName::StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="bdcb2-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="bdcb2-103">指定したアセンブリに対して厳密な名前の署名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdcb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="bdcb2-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdcb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdcb2-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bdcb2-106">[in]厳密な名前の署名を生成するアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="bdcb2-107">[in]公開/秘密キー ペアを格納するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="bdcb2-108">場合`pbKeyBlob`が null、`wszKeyContainer`暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="bdcb2-109">ここでは、コンテナーに格納されているキーのペアは、ファイルの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="bdcb2-110">場合`pbKeyBlob`が null でないと見なされます、キーのペア キー バイナリ ラージ オブジェクト (BLOB) に格納します。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="bdcb2-111">キーは、1024 ビット Rivest-Shamir-Adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="bdcb2-112">この時点でその他の種類のキーがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="bdcb2-113">[in]公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="bdcb2-114">このペアは、Win32 によって作成された形式で、`CryptExportKey`関数。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="bdcb2-115">場合`pbKeyBlob`が null で指定されたキー コンテナー`wszKeyContainer`キー ペアを格納すると見なされます。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="bdcb2-116">[in]サイズ (バイト単位) の`pbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="bdcb2-117">[out]共通言語ランタイムには、署名を返す位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="bdcb2-118">場合`ppbSignatureBlob`が null の場合、ランタイム、シグネチャ ファイルに格納で指定された`wszFilePath`します。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="bdcb2-119">場合`ppbSignatureBlob`が null でない共通言語ランタイム割り当て領域が、署名を返します。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="bdcb2-120">使用して呼び出し元がこの領域を解放する必要があります、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="bdcb2-121">[out]返される署名のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdcb2-122">戻り値</span><span class="sxs-lookup"><span data-stu-id="bdcb2-122">Return Value</span></span>  
 <span data-ttu-id="bdcb2-123">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdcb2-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="bdcb2-124">Remarks</span></span>  
 <span data-ttu-id="bdcb2-125">Null を指定`wszFilePath`署名を作成することがなく、署名のサイズを計算します。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="bdcb2-126">署名は、ファイルに直接格納または呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdcb2-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="bdcb2-127">Requirements</span></span>  
 <span data-ttu-id="bdcb2-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdcb2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdcb2-129">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bdcb2-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bdcb2-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bdcb2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdcb2-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdcb2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdcb2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdcb2-132">See also</span></span>

- [<span data-ttu-id="bdcb2-133">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="bdcb2-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="bdcb2-134">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bdcb2-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
