---
title: IMetaDataEmit2::DefineMethodSpec メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: a5d9342b8bfe650106ccf9daf2a91dfbcd575446
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175540"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="2ab0e-102">IMetaDataEmit2::DefineMethodSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="2ab0e-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="2ab0e-103">メソッドのジェネリック インスタンスを作成し、定義に対するトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ab0e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab0e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ab0e-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="2ab0e-106">[in]ジェネリック インスタンスを作成するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="2ab0e-107">トークンは型`mdMethodDef`または`mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="2ab0e-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2ab0e-108">[in]メソッドのバイナリ COM+ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="2ab0e-109">[in]のサイズ (バイト単位)`pvSigBlob`です。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="2ab0e-110">[アウト]メソッドのメタデータ シグネチャ定義へのトークン。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab0e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ab0e-111">Requirements</span></span>  
 <span data-ttu-id="2ab0e-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab0e-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="2ab0e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ab0e-114">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ab0e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ab0e-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab0e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab0e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ab0e-116">See also</span></span>

- [<span data-ttu-id="2ab0e-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ab0e-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2ab0e-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ab0e-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
