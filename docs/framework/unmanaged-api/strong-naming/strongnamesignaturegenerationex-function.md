---
title: StrongNameSignatureGenerationEx 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
ms.openlocfilehash: e8f63a6379af8f2b7b88c511840622d49d65d587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141578"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="75f90-102">StrongNameSignatureGenerationEx 関数</span><span class="sxs-lookup"><span data-stu-id="75f90-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="75f90-103">指定したフラグに従って、指定したアセンブリの厳密な名前の署名を生成します。</span><span class="sxs-lookup"><span data-stu-id="75f90-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="75f90-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="75f90-104">This function has been deprecated.</span></span> <span data-ttu-id="75f90-105">代わりに[ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="75f90-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f90-106">構文</span><span class="sxs-lookup"><span data-stu-id="75f90-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75f90-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75f90-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="75f90-108">から厳密な名前の署名が生成されるアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="75f90-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="75f90-109">から公開キーと秘密キーのペアを格納するキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="75f90-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="75f90-110">`pbKeyBlob` が null の場合、`wszKeyContainer` は暗号化サービスプロバイダー (CSP) 内の有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75f90-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="75f90-111">この場合、コンテナーに格納されているキーペアがファイルの署名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="75f90-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="75f90-112">`pbKeyBlob` が null でない場合、キーのペアは、バイナリラージオブジェクト (BLOB) に格納されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="75f90-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="75f90-113">から公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75f90-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="75f90-114">このペアは、Win32 `CryptExportKey` 関数によって作成される形式です。</span><span class="sxs-lookup"><span data-stu-id="75f90-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="75f90-115">`pbKeyBlob` が null の場合、`wszKeyContainer` によって指定されたキーコンテナーには、キーのペアが含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="75f90-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="75f90-116">から`pbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="75f90-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="75f90-117">入出力共通言語ランタイムが署名を返す場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="75f90-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="75f90-118">`ppbSignatureBlob` が null の場合、ランタイムは `wszFilePath`によって指定されたファイルに署名を格納します。</span><span class="sxs-lookup"><span data-stu-id="75f90-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="75f90-119">`ppbSignatureBlob` が null でない場合は、共通言語ランタイムによって、署名を返す領域が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="75f90-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="75f90-120">呼び出し元は、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を使用してこの領域を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75f90-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="75f90-121">入出力返されたシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="75f90-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="75f90-122">から次の値の1つまたは複数です。</span><span class="sxs-lookup"><span data-stu-id="75f90-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="75f90-123">`SN_SIGN_ALL_FILES` (0x00000001)-リンクされたモジュールのすべてのハッシュを再計算します。</span><span class="sxs-lookup"><span data-stu-id="75f90-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="75f90-124">`SN_TEST_SIGN` (0x00000002)-アセンブリにテスト署名します。</span><span class="sxs-lookup"><span data-stu-id="75f90-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75f90-125">戻り値</span><span class="sxs-lookup"><span data-stu-id="75f90-125">Return Value</span></span>  
 <span data-ttu-id="75f90-126">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="75f90-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75f90-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="75f90-127">Remarks</span></span>  
 <span data-ttu-id="75f90-128">署名を作成せずに署名のサイズを計算するには、`wszFilePath` に null を指定します。</span><span class="sxs-lookup"><span data-stu-id="75f90-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="75f90-129">署名は、ファイルに直接格納するか、呼び出し元に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="75f90-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="75f90-130">`SN_SIGN_ALL_FILES` が指定されていても、公開キーが含まれていない場合 (`pbKeyBlob` と `wszFilePath` の両方が null の場合)、リンクモジュールのハッシュは再計算されますが、アセンブリは再署名されません。</span><span class="sxs-lookup"><span data-stu-id="75f90-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="75f90-131">`SN_TEST_SIGN` が指定されている場合、共通言語ランタイムヘッダーは、アセンブリが厳密な名前で署名されていることを示すために変更されません。</span><span class="sxs-lookup"><span data-stu-id="75f90-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="75f90-132">`StrongNameSignatureGenerationEx` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="75f90-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75f90-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="75f90-133">Requirements</span></span>  
 <span data-ttu-id="75f90-134">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75f90-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75f90-135">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="75f90-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="75f90-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="75f90-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75f90-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75f90-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f90-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="75f90-138">See also</span></span>

- [<span data-ttu-id="75f90-139">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="75f90-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="75f90-140">StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="75f90-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="75f90-141">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75f90-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
