---
title: IMetaDataEmit::DefineMethodImpl メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05b2530bde2f4532e94610a683e7bbc2f59540aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178387"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="94f87-102">IMetaDataEmit::DefineMethodImpl メソッド</span><span class="sxs-lookup"><span data-stu-id="94f87-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="94f87-103">インターフェイスから継承されたメソッドの実装の定義を作成し、そのメソッドの実装定義にトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="94f87-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f87-104">構文</span><span class="sxs-lookup"><span data-stu-id="94f87-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94f87-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="94f87-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="94f87-106">[in]`mdTypedef`実装するクラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="94f87-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="94f87-107">[in]`mdMethodDef`または`mdMethodRef`コード本体のトークン。</span><span class="sxs-lookup"><span data-stu-id="94f87-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="94f87-108">[in]`mdMethodDef`または`mdMethodRef`に実装されているインターフェイス メソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="94f87-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94f87-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="94f87-109">Requirements</span></span>  
 <span data-ttu-id="94f87-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f87-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94f87-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94f87-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94f87-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="94f87-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94f87-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94f87-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f87-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="94f87-114">See also</span></span>

- [<span data-ttu-id="94f87-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94f87-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="94f87-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94f87-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
