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
ms.openlocfilehash: 9ab6fcb64e4654302e411d4dcc587df2e0bf1dc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125189"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="846d6-102">StrongNameSignatureGeneration 関数</span><span class="sxs-lookup"><span data-stu-id="846d6-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="846d6-103">指定したアセンブリに対して厳密な名前の署名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="846d6-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="846d6-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="846d6-104">This function has been deprecated.</span></span> <span data-ttu-id="846d6-105">代わりに[ICLRStrongName:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="846d6-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="846d6-106">構文</span><span class="sxs-lookup"><span data-stu-id="846d6-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="846d6-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="846d6-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="846d6-108">から厳密な名前の署名が生成されるアセンブリのマニフェストを含むファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="846d6-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="846d6-109">から公開キーと秘密キーのペアを格納するキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="846d6-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="846d6-110">`pbKeyBlob` が null の場合、`wszKeyContainer` は暗号化サービスプロバイダー (CSP) 内の有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="846d6-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="846d6-111">この場合、コンテナーに格納されているキーペアがファイルの署名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="846d6-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="846d6-112">`pbKeyBlob` が null でない場合、キーのペアは、バイナリラージオブジェクト (BLOB) に格納されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="846d6-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="846d6-113">キーは 1024-Rivest-shamir-adleman-Rivest-shamir-adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="846d6-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="846d6-114">この時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="846d6-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="846d6-115">から公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="846d6-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="846d6-116">このペアは、Win32 `CryptExportKey` 関数によって作成される形式です。</span><span class="sxs-lookup"><span data-stu-id="846d6-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="846d6-117">`pbKeyBlob` が null の場合、`wszKeyContainer` によって指定されたキーコンテナーには、キーのペアが含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="846d6-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="846d6-118">から`pbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="846d6-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="846d6-119">入出力共通言語ランタイムが署名を返す場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="846d6-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="846d6-120">`ppbSignatureBlob` が null の場合、ランタイムは `wszFilePath`によって指定されたファイルに署名を格納します。</span><span class="sxs-lookup"><span data-stu-id="846d6-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="846d6-121">`ppbSignatureBlob` が null でない場合は、共通言語ランタイムによって、署名を返す領域が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="846d6-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="846d6-122">呼び出し元は、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を使用してこの領域を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="846d6-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="846d6-123">入出力返されたシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="846d6-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="846d6-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="846d6-124">Return Value</span></span>  
 <span data-ttu-id="846d6-125">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="846d6-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="846d6-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="846d6-126">Remarks</span></span>  
 <span data-ttu-id="846d6-127">署名を作成せずに署名のサイズを計算するには、`wszFilePath` に null を指定します。</span><span class="sxs-lookup"><span data-stu-id="846d6-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="846d6-128">署名は、ファイルに直接格納するか、呼び出し元に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="846d6-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="846d6-129">`StrongNameSignatureGeneration` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="846d6-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="846d6-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="846d6-130">Requirements</span></span>  
 <span data-ttu-id="846d6-131">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="846d6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="846d6-132">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="846d6-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="846d6-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="846d6-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="846d6-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="846d6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846d6-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="846d6-135">See also</span></span>

- [<span data-ttu-id="846d6-136">StrongNameSignatureGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="846d6-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="846d6-137">StrongNameSignatureGenerationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="846d6-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="846d6-138">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="846d6-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
