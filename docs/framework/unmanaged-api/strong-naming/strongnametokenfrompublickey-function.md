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
ms.openlocfilehash: b95c96efeb666f25d04118aa8cb9b0da3a2e7924
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104159"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="1dc4a-102">StrongNameTokenFromPublicKey 関数</span><span class="sxs-lookup"><span data-stu-id="1dc4a-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="1dc4a-103">公開キーを表すトークンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-103">Gets a token representing a public key.</span></span> <span data-ttu-id="1dc4a-104">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="1dc4a-105">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-105">This function has been deprecated.</span></span> <span data-ttu-id="1dc4a-106">代わりに[ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc4a-107">構文</span><span class="sxs-lookup"><span data-stu-id="1dc4a-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dc4a-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1dc4a-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="1dc4a-109">から厳密な名前の署名を生成するために使用されるキーペアの公開部分を格納する[Publickeyblob](publickeyblob-structure.md)型の構造体。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="1dc4a-110">から`pbPublicKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="1dc4a-111">入出力`pbPublicKeyBlob`渡されたキーに対応する厳密な名前トークン。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="1dc4a-112">共通言語ランタイムは、トークンを返すメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="1dc4a-113">呼び出し元は、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を使用して、このメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="1dc4a-114">入出力返された厳密な名前トークンのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dc4a-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="1dc4a-115">Return Value</span></span>  
 <span data-ttu-id="1dc4a-116">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dc4a-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="1dc4a-117">Remarks</span></span>  
 <span data-ttu-id="1dc4a-118">厳密な名前トークンは、キー情報をメタデータに格納するときに領域を節約するために使用される公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="1dc4a-119">具体的には、アセンブリ参照では、依存アセンブリを参照するために厳密な名前トークンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="1dc4a-120">`StrongNameTokenFromPublicKey` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dc4a-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="1dc4a-121">Requirements</span></span>  
 <span data-ttu-id="1dc4a-122">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dc4a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dc4a-123">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="1dc4a-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1dc4a-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1dc4a-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="1dc4a-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dc4a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dc4a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dc4a-126">See also</span></span>

- [<span data-ttu-id="1dc4a-127">StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="1dc4a-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="1dc4a-128">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="1dc4a-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="1dc4a-129">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="1dc4a-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
