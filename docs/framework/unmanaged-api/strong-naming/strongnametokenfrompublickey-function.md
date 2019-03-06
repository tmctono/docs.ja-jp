---
title: StrongNameTokenFromPublicKey 関数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b095d999f1e7e37c068c800e66f56c293422127
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490399"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="44c08-102">StrongNameTokenFromPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="44c08-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="44c08-103">公開キーを表すトークンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="44c08-103">Gets a token representing a public key.</span></span> <span data-ttu-id="44c08-104">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="44c08-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="44c08-105">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="44c08-105">This function has been deprecated.</span></span> <span data-ttu-id="44c08-106">使用して、 [iclrstrongname::strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="44c08-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c08-107">構文</span><span class="sxs-lookup"><span data-stu-id="44c08-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c08-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44c08-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="44c08-109">[in]型の構造体[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)厳密な名前の署名を生成するためのキー ペアの公開部分を格納しています。</span><span class="sxs-lookup"><span data-stu-id="44c08-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="44c08-110">[in]サイズ (バイト単位) の`pbPublicKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="44c08-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="44c08-111">[out]渡されたキーに対応する厳密な名前トークン`pbPublicKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="44c08-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="44c08-112">共通言語ランタイムでは、トークンが返されるメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="44c08-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="44c08-113">呼び出し元を使用してこのメモリを解放する必要があります、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="44c08-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="44c08-114">[out]厳密な名前が返されたトークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="44c08-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44c08-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="44c08-115">Return Value</span></span>  
 <span data-ttu-id="44c08-116">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="44c08-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44c08-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="44c08-117">Remarks</span></span>  
 <span data-ttu-id="44c08-118">厳密な名前トークンは、メタデータにキー情報を格納する場合は、スペースを節約するために使用する公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="44c08-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="44c08-119">具体的には、厳密な名前トークンは、依存アセンブリを参照するアセンブリ参照で使用されます。</span><span class="sxs-lookup"><span data-stu-id="44c08-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="44c08-120">場合、`StrongNameTokenFromPublicKey`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="44c08-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c08-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="44c08-121">Requirements</span></span>  
 <span data-ttu-id="44c08-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c08-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c08-123">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="44c08-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="44c08-124">**ライブラリ:** Mscoree.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="44c08-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="44c08-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c08-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c08-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="44c08-126">See also</span></span>
- [<span data-ttu-id="44c08-127">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="44c08-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="44c08-128">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="44c08-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="44c08-129">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="44c08-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
