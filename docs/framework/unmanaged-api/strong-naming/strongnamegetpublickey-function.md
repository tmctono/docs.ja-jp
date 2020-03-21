---
title: StrongNameGetPublicKey 関数
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176930"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="3959d-102">StrongNameGetPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="3959d-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="3959d-103">秘密/公開キーの組から公開キーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="3959d-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="3959d-104">キー ペアは、暗号化サービス プロバイダー (CSP) 内のキー コンテナー名またはバイトの生のコレクションとして提供できます。</span><span class="sxs-lookup"><span data-stu-id="3959d-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="3959d-105">この関数は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="3959d-105">This function has been deprecated.</span></span> <span data-ttu-id="3959d-106">代わりに[、メソッド](../hosting/iclrstrongname-strongnamegetpublickey-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3959d-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3959d-107">構文</span><span class="sxs-lookup"><span data-stu-id="3959d-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3959d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3959d-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="3959d-109">[in]公開キーと秘密キーのペアを含むキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="3959d-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="3959d-110">null`pbKeyBlob`の場合`szKeyContainer`は、CSP 内で有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3959d-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="3959d-111">この場合、`StrongNameGetPublicKey`コンテナに格納されているキーペアから公開キーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="3959d-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="3959d-112">null`pbKeyBlob`でない場合、キー ペアは、キー のバイナリ ラージ オブジェクト (BLOB) に含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="3959d-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="3959d-113">キーは、1024 ビットのリベスト シャミール-アドレマン (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3959d-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="3959d-114">現時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3959d-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="3959d-115">[in]公開キーと秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3959d-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="3959d-116">このペアは、Win32`CryptExportKey`関数によって作成された形式です。</span><span class="sxs-lookup"><span data-stu-id="3959d-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="3959d-117">null`pbKeyBlob`の場合、指定されたキー`szKeyContainer`コンテナーにはキー ペアが含まれるものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="3959d-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="3959d-118">[in]のサイズ (バイト単位)`pbKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="3959d-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="3959d-119">[アウト]返された公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="3959d-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="3959d-120">パラメーター`ppbPublicKeyBlob`は、共通言語ランタイムによって割り当てられ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="3959d-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="3959d-121">呼び出し元は[、関数](strongnamefreebuffer-function.md)を使用してメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3959d-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="3959d-122">[アウト]返される公開キー BLOB のサイズ。</span><span class="sxs-lookup"><span data-stu-id="3959d-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3959d-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="3959d-123">Return Value</span></span>  
 <span data-ttu-id="3959d-124">`true`正常に完了した場合。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="3959d-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3959d-125">解説</span><span class="sxs-lookup"><span data-stu-id="3959d-125">Remarks</span></span>  
 <span data-ttu-id="3959d-126">公開キーは[、パブリックキー Blob](publickeyblob-structure.md)構造体に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3959d-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="3959d-127">関数が`StrongNameGetPublicKey`正常に完了しない場合は、[関数](strongnameerrorinfo-function.md)を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3959d-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3959d-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="3959d-128">Requirements</span></span>  
 <span data-ttu-id="3959d-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3959d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3959d-130">**ヘッダー:** ストロングネーム.h</span><span class="sxs-lookup"><span data-stu-id="3959d-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3959d-131">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="3959d-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3959d-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3959d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3959d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="3959d-133">See also</span></span>

- [<span data-ttu-id="3959d-134">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="3959d-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="3959d-135">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="3959d-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="3959d-136">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3959d-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="3959d-137">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="3959d-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
