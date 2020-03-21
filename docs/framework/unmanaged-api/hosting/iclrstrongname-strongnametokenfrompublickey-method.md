---
title: ICLRStrongName::StrongNameTokenFromPublicKey メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176319"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="dc330-102">ICLRStrongName::StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="dc330-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="dc330-103">公開キーを表すトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc330-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="dc330-104">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="dc330-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc330-105">構文</span><span class="sxs-lookup"><span data-stu-id="dc330-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc330-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc330-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="dc330-107">[in]厳密な名前の署名を生成するために使用されるキー ペアのパブリック部分を含む[、型の PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)の構造体。</span><span class="sxs-lookup"><span data-stu-id="dc330-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="dc330-108">[in]のサイズ (バイト単位)`pbPublicKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="dc330-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="dc330-109">[アウト]渡されたキーに対応する厳密な名前トークン`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="dc330-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="dc330-110">共通言語ランタイムは、トークンを返すメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dc330-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="dc330-111">呼び出し元は、メソッドを使用してこのメモリ[を](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc330-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="dc330-112">[アウト]返された厳密な名前トークンのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="dc330-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc330-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="dc330-113">Return Value</span></span>  
 <span data-ttu-id="dc330-114">`S_OK`メソッドが正常に完了した場合。それ以外の場合は、失敗を示す HRESULT 値です (リストの[HRESULT の共通値](/windows/win32/seccrypto/common-hresult-values)を参照)。</span><span class="sxs-lookup"><span data-stu-id="dc330-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc330-115">解説</span><span class="sxs-lookup"><span data-stu-id="dc330-115">Remarks</span></span>  
 <span data-ttu-id="dc330-116">厳密な名前トークンは、メタデータにキー情報を格納するときに領域を節約するために使用される公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="dc330-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="dc330-117">特に、厳密な名前トークンは、依存アセンブリを参照するためにアセンブリ参照で使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc330-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc330-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc330-118">Requirements</span></span>  
 <span data-ttu-id="dc330-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc330-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc330-120">**ヘッダー:** メタホスト.h</span><span class="sxs-lookup"><span data-stu-id="dc330-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dc330-121">**ライブラリ:** mscoree.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="dc330-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="dc330-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc330-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc330-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc330-123">See also</span></span>

- [<span data-ttu-id="dc330-124">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="dc330-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="dc330-125">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="dc330-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="dc330-126">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc330-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
