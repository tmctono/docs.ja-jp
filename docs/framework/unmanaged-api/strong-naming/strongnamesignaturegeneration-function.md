---
title: StrongNameSignatureGeneration 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176904"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="d8370-102">StrongNameSignatureGeneration 関数</span><span class="sxs-lookup"><span data-stu-id="d8370-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="d8370-103">指定したアセンブリに対して厳密な名前の署名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8370-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="d8370-104">この関数は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="d8370-104">This function has been deprecated.</span></span> <span data-ttu-id="d8370-105">代わりに[、メソッド](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8370-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8370-106">構文</span><span class="sxs-lookup"><span data-stu-id="d8370-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8370-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8370-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d8370-108">[in]厳密な名前の署名が生成されるアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="d8370-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="d8370-109">[in]公開キーと秘密キーのペアを含むキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="d8370-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="d8370-110">null`pbKeyBlob`の場合`wszKeyContainer`は、暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8370-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="d8370-111">この場合、コンテナーに格納されているキーペアを使用してファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="d8370-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="d8370-112">null`pbKeyBlob`でない場合、キー ペアは、キー のバイナリ ラージ オブジェクト (BLOB) に含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="d8370-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="d8370-113">キーは、1024 ビットのリベスト シャミール-アドレマン (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8370-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="d8370-114">現時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d8370-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d8370-115">[in]公開キーと秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d8370-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d8370-116">このペアは、Win32`CryptExportKey`関数によって作成された形式です。</span><span class="sxs-lookup"><span data-stu-id="d8370-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d8370-117">null`pbKeyBlob`の場合、指定されたキー`wszKeyContainer`コンテナーにはキー ペアが含まれるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="d8370-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d8370-118">[in]のサイズ (バイト単位)`pbKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="d8370-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="d8370-119">[アウト]共通言語ランタイムが署名を返す場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d8370-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="d8370-120">null`ppbSignatureBlob`の場合、ランタイムは、 で指定されたファイルに`wszFilePath`署名を格納します。</span><span class="sxs-lookup"><span data-stu-id="d8370-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="d8370-121">null`ppbSignatureBlob`でない場合、共通言語ランタイムは、署名を返す領域を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d8370-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="d8370-122">呼び出し元は[、厳密な名前フリーバッファー](strongnamefreebuffer-function.md)関数を使用して、この領域を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8370-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="d8370-123">[アウト]返されたシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d8370-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8370-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="d8370-124">Return Value</span></span>  
 <span data-ttu-id="d8370-125">`true`正常に完了した場合。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="d8370-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8370-126">解説</span><span class="sxs-lookup"><span data-stu-id="d8370-126">Remarks</span></span>  
 <span data-ttu-id="d8370-127">署名を`wszFilePath`作成せずに署名のサイズを計算するには、 に null を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8370-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="d8370-128">署名は、ファイルに直接格納するか、または呼び出し元に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d8370-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="d8370-129">関数が`StrongNameSignatureGeneration`正常に完了しない場合は、[関数](strongnameerrorinfo-function.md)を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8370-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8370-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8370-130">Requirements</span></span>  
 <span data-ttu-id="d8370-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8370-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8370-132">**ヘッダー:** ストロングネーム.h</span><span class="sxs-lookup"><span data-stu-id="d8370-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d8370-133">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="d8370-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8370-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8370-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8370-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8370-135">See also</span></span>

- [<span data-ttu-id="d8370-136">StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="d8370-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="d8370-137">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="d8370-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="d8370-138">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8370-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
