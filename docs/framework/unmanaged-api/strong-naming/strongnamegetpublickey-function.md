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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799063"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="c6b38-102">StrongNameGetPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="c6b38-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="c6b38-103">秘密/公開キーの組から公開キーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="c6b38-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="c6b38-104">キーペアは、暗号化サービスプロバイダー (CSP) 内のキーコンテナー名として、またはバイトの未加工コレクションとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6b38-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="c6b38-105">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="c6b38-105">This function has been deprecated.</span></span> <span data-ttu-id="c6b38-106">代わりに[ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c6b38-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b38-107">構文</span><span class="sxs-lookup"><span data-stu-id="c6b38-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6b38-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6b38-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="c6b38-109">から公開キーと秘密キーのペアを格納するキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="c6b38-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="c6b38-110">が`pbKeyBlob` null の場合`szKeyContainer` 、は CSP 内の有効なコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b38-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="c6b38-111">この場合、は`StrongNameGetPublicKey` 、コンテナーに格納されているキーペアから公開キーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c6b38-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="c6b38-112">が`pbKeyBlob` null でない場合、キーペアは、バイナリラージオブジェクト (BLOB) に格納されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="c6b38-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="c6b38-113">キーは 1024-Rivest-shamir-adleman-Rivest-shamir-adleman (RSA) 署名キーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b38-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="c6b38-114">この時点では、他の種類のキーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c6b38-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c6b38-115">から公開/秘密キーのペアへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c6b38-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c6b38-116">このペアは、Win32 `CryptExportKey`関数によって作成される形式です。</span><span class="sxs-lookup"><span data-stu-id="c6b38-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c6b38-117">が`pbKeyBlob` null の場合、によって指定`szKeyContainer`されたキーコンテナーには、キーのペアが含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="c6b38-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c6b38-118">からの`pbKeyBlob`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c6b38-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c6b38-119">入出力返された公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="c6b38-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="c6b38-120">`ppbPublicKeyBlob`パラメーターは、共通言語ランタイムによって割り当てられ、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="c6b38-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="c6b38-121">呼び出し元は、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を使用してメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b38-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c6b38-122">入出力返される公開キー BLOB のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c6b38-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6b38-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="c6b38-123">Return Value</span></span>  
 <span data-ttu-id="c6b38-124">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="c6b38-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6b38-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6b38-125">Remarks</span></span>  
 <span data-ttu-id="c6b38-126">公開キーは[Publickeyblob](publickeyblob-structure.md)構造に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6b38-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="c6b38-127">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameGetPublicKey`</span><span class="sxs-lookup"><span data-stu-id="c6b38-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6b38-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6b38-128">Requirements</span></span>  
 <span data-ttu-id="c6b38-129">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b38-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6b38-130">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="c6b38-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c6b38-131">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c6b38-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6b38-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6b38-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b38-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6b38-133">See also</span></span>

- [<span data-ttu-id="c6b38-134">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="c6b38-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="c6b38-135">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="c6b38-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="c6b38-136">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6b38-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="c6b38-137">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="c6b38-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
