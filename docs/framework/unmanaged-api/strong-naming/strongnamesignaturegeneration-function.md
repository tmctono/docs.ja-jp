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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1abb7efe0f30ff14d51f9486d6d5b04d2faa053
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773750"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="66dca-102">StrongNameSignatureGeneration 関数</span><span class="sxs-lookup"><span data-stu-id="66dca-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="66dca-103">指定したアセンブリに対して厳密な名前の署名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="66dca-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="66dca-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="66dca-104">This function has been deprecated.</span></span> <span data-ttu-id="66dca-105">使用して、 [iclrstrongname::strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="66dca-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66dca-106">構文</span><span class="sxs-lookup"><span data-stu-id="66dca-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="66dca-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66dca-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="66dca-108">[in]厳密な名前の署名を生成するアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66dca-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="66dca-109">[in]公開/秘密キー ペアを格納するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="66dca-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="66dca-110">場合`pbKeyBlob`が null、`wszKeyContainer`暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66dca-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="66dca-111">ここでは、コンテナーに格納されているキーのペアは、ファイルの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="66dca-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="66dca-112">場合`pbKeyBlob`が null でないと見なされます、キーのペア キー バイナリ ラージ オブジェクト (BLOB) に格納します。</span><span class="sxs-lookup"><span data-stu-id="66dca-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="66dca-113">キーは、1024 ビット Rivest-Shamir-Adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="66dca-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="66dca-114">この時点でその他の種類のキーがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="66dca-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="66dca-115">[in]公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="66dca-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="66dca-116">このペアは、Win32 によって作成された形式で、`CryptExportKey`関数。</span><span class="sxs-lookup"><span data-stu-id="66dca-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="66dca-117">場合`pbKeyBlob`が null で指定されたキー コンテナー`wszKeyContainer`キー ペアを格納すると見なされます。</span><span class="sxs-lookup"><span data-stu-id="66dca-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="66dca-118">[in]サイズ (バイト単位) の`pbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="66dca-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="66dca-119">[out]共通言語ランタイムには、署名を返す位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="66dca-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="66dca-120">場合`ppbSignatureBlob`が null の場合、ランタイム、シグネチャ ファイルに格納で指定された`wszFilePath`します。</span><span class="sxs-lookup"><span data-stu-id="66dca-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="66dca-121">場合`ppbSignatureBlob`が null でない共通言語ランタイム割り当て領域が、署名を返します。</span><span class="sxs-lookup"><span data-stu-id="66dca-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="66dca-122">呼び出し元が使用して、この領域を解放する必要があります、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="66dca-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="66dca-123">[out]返される署名のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="66dca-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66dca-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="66dca-124">Return Value</span></span>  
 <span data-ttu-id="66dca-125">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="66dca-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66dca-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="66dca-126">Remarks</span></span>  
 <span data-ttu-id="66dca-127">Null を指定`wszFilePath`署名を作成することがなく、署名のサイズを計算します。</span><span class="sxs-lookup"><span data-stu-id="66dca-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="66dca-128">署名は、ファイルに直接格納または呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="66dca-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="66dca-129">場合、`StrongNameSignatureGeneration`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="66dca-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66dca-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="66dca-130">Requirements</span></span>  
 <span data-ttu-id="66dca-131">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dca-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66dca-132">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="66dca-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="66dca-133">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="66dca-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66dca-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66dca-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66dca-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="66dca-135">See also</span></span>

- [<span data-ttu-id="66dca-136">StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="66dca-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="66dca-137">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="66dca-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="66dca-138">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66dca-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
