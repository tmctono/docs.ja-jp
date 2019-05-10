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
ms.openlocfilehash: 059dadcaf7a55074e30c59873a8c1e7016b0a33e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666005"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="74bfd-102">StrongNameSignatureGenerationEx 関数</span><span class="sxs-lookup"><span data-stu-id="74bfd-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="74bfd-103">指定したフラグに基づいて、指定されたアセンブリの厳密な名前の署名を生成します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="74bfd-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="74bfd-104">This function has been deprecated.</span></span> <span data-ttu-id="74bfd-105">使用して、 [iclrstrongname::strongnamesignaturegenerationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="74bfd-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74bfd-106">構文</span><span class="sxs-lookup"><span data-stu-id="74bfd-106">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="74bfd-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74bfd-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="74bfd-108">[in]厳密な名前の署名を生成するアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="74bfd-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="74bfd-109">[in]公開/秘密キー ペアを格納するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="74bfd-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="74bfd-110">場合`pbKeyBlob`が null、`wszKeyContainer`暗号化サービス プロバイダー (CSP) 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74bfd-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="74bfd-111">ここでは、コンテナーに格納されているキーのペアは、ファイルの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="74bfd-112">場合`pbKeyBlob`が null でないと見なされます、キーのペア キー バイナリ ラージ オブジェクト (BLOB) に格納します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="74bfd-113">[in]公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="74bfd-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="74bfd-114">このペアは、Win32 によって作成された形式で、`CryptExportKey`関数。</span><span class="sxs-lookup"><span data-stu-id="74bfd-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="74bfd-115">場合`pbKeyBlob`が null で指定されたキー コンテナー`wszKeyContainer`キー ペアを格納すると見なされます。</span><span class="sxs-lookup"><span data-stu-id="74bfd-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="74bfd-116">[in]サイズ (バイト単位) の`pbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="74bfd-117">[out]共通言語ランタイムには、署名を返す位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="74bfd-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="74bfd-118">場合`ppbSignatureBlob`が null の場合、ランタイム、シグネチャ ファイルに格納で指定された`wszFilePath`します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="74bfd-119">場合`ppbSignatureBlob`が null でない共通言語ランタイム割り当て領域が、署名を返します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="74bfd-120">呼び出し元が使用して、この領域を解放する必要があります、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="74bfd-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="74bfd-121">[out]返される署名のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="74bfd-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="74bfd-122">[in]1 つ以上の次の値。</span><span class="sxs-lookup"><span data-stu-id="74bfd-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="74bfd-123">`SN_SIGN_ALL_FILES` (0x00000001) - リンクされたモジュールのすべてのハッシュを再計算します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="74bfd-124">`SN_TEST_SIGN` (0x00000002) - テスト アセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74bfd-125">戻り値</span><span class="sxs-lookup"><span data-stu-id="74bfd-125">Return Value</span></span>  
 <span data-ttu-id="74bfd-126">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74bfd-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="74bfd-127">Remarks</span></span>  
 <span data-ttu-id="74bfd-128">Null を指定`wszFilePath`署名を作成することがなく、署名のサイズを計算します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="74bfd-129">署名は、いずれか、ファイルに直接格納または呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="74bfd-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="74bfd-130">場合`SN_SIGN_ALL_FILES`が指定されてが公開キーは含まれません (両方`pbKeyBlob`と`wszFilePath`が null の場合)、リンクされたモジュールのハッシュが再計算されますが、アセンブリは、再署名することはありません。</span><span class="sxs-lookup"><span data-stu-id="74bfd-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="74bfd-131">場合`SN_TEST_SIGN`を指定すると、共通言語ランタイム ヘッダーは、アセンブリが厳密な名前で署名されているかを示すには変更されません。</span><span class="sxs-lookup"><span data-stu-id="74bfd-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="74bfd-132">場合、`StrongNameSignatureGenerationEx`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="74bfd-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74bfd-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="74bfd-133">Requirements</span></span>  
 <span data-ttu-id="74bfd-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bfd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74bfd-135">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="74bfd-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="74bfd-136">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="74bfd-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74bfd-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74bfd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bfd-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="74bfd-138">See also</span></span>

- [<span data-ttu-id="74bfd-139">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="74bfd-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="74bfd-140">StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="74bfd-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="74bfd-141">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74bfd-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
