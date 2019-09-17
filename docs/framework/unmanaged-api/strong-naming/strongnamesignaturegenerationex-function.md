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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798984"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="19e58-102">StrongNameSignatureGenerationEx 関数</span><span class="sxs-lookup"><span data-stu-id="19e58-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="19e58-103">指定したフラグに従って、指定したアセンブリの厳密な名前の署名を生成します。</span><span class="sxs-lookup"><span data-stu-id="19e58-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="19e58-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="19e58-104">This function has been deprecated.</span></span> <span data-ttu-id="19e58-105">代わりに[ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="19e58-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19e58-106">構文</span><span class="sxs-lookup"><span data-stu-id="19e58-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="19e58-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19e58-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="19e58-108">から厳密な名前の署名が生成されるアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="19e58-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="19e58-109">から公開キーと秘密キーのペアを格納するキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="19e58-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="19e58-110">が`pbKeyBlob` null の場合`wszKeyContainer` 、では、暗号化サービスプロバイダー (CSP) 内の有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e58-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="19e58-111">この場合、コンテナーに格納されているキーペアがファイルの署名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="19e58-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="19e58-112">が`pbKeyBlob` null でない場合、キーペアは、バイナリラージオブジェクト (BLOB) に格納されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="19e58-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="19e58-113">から公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="19e58-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="19e58-114">このペアは、Win32 `CryptExportKey`関数によって作成される形式です。</span><span class="sxs-lookup"><span data-stu-id="19e58-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="19e58-115">が`pbKeyBlob` null の場合、によって指定`wszKeyContainer`されたキーコンテナーには、キーのペアが含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="19e58-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="19e58-116">からの`pbKeyBlob`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="19e58-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="19e58-117">入出力共通言語ランタイムが署名を返す場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="19e58-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="19e58-118">が`ppbSignatureBlob` null の場合、ランタイムはによって`wszFilePath`指定されたファイルに署名を格納します。</span><span class="sxs-lookup"><span data-stu-id="19e58-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="19e58-119">が`ppbSignatureBlob` null でない場合は、共通言語ランタイムによって、署名を返す領域が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="19e58-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="19e58-120">呼び出し元は、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を使用してこの領域を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e58-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="19e58-121">入出力返されたシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="19e58-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="19e58-122">から次の値の1つまたは複数です。</span><span class="sxs-lookup"><span data-stu-id="19e58-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="19e58-123">`SN_SIGN_ALL_FILES`(0x00000001)-リンクされたモジュールのすべてのハッシュを再計算します。</span><span class="sxs-lookup"><span data-stu-id="19e58-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="19e58-124">`SN_TEST_SIGN`(0x00000002)-アセンブリに対してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="19e58-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19e58-125">戻り値</span><span class="sxs-lookup"><span data-stu-id="19e58-125">Return Value</span></span>  
 <span data-ttu-id="19e58-126">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="19e58-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19e58-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="19e58-127">Remarks</span></span>  
 <span data-ttu-id="19e58-128">署名を作成`wszFilePath`せずに署名のサイズを計算するには、に null を指定します。</span><span class="sxs-lookup"><span data-stu-id="19e58-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="19e58-129">署名は、ファイルに直接格納するか、呼び出し元に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="19e58-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="19e58-130">が`SN_SIGN_ALL_FILES`指定されていても、公開キーが`pbKeyBlob`含ま`wszFilePath`れていない場合 (との両方が null の場合)、リンクされたモジュールのハッシュは再計算されますが、アセンブリは再署名されません。</span><span class="sxs-lookup"><span data-stu-id="19e58-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="19e58-131">が`SN_TEST_SIGN`指定されている場合、共通言語ランタイムヘッダーは、アセンブリが厳密な名前で署名されていることを示すために変更されません。</span><span class="sxs-lookup"><span data-stu-id="19e58-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="19e58-132">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameSignatureGenerationEx`</span><span class="sxs-lookup"><span data-stu-id="19e58-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19e58-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="19e58-133">Requirements</span></span>  
 <span data-ttu-id="19e58-134">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19e58-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e58-135">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="19e58-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="19e58-136">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="19e58-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19e58-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e58-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e58-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="19e58-138">See also</span></span>

- [<span data-ttu-id="19e58-139">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="19e58-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="19e58-140">StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="19e58-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="19e58-141">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19e58-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
