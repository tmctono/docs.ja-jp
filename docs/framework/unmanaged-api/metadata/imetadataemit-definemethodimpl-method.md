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
ms.openlocfilehash: b64275def01d7b62f9a461de69a286769094305e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777586"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="03792-102">IMetaDataEmit::DefineMethodImpl メソッド</span><span class="sxs-lookup"><span data-stu-id="03792-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="03792-103">インターフェイスから継承されたメソッドの実装の定義を作成し、そのメソッドの実装定義にトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="03792-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03792-104">構文</span><span class="sxs-lookup"><span data-stu-id="03792-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03792-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03792-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="03792-106">[in]`mdTypedef`実装するクラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="03792-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="03792-107">[in]`mdMethodDef`または`mdMemberRef`コード本体のトークン。</span><span class="sxs-lookup"><span data-stu-id="03792-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="03792-108">[in]`mdMethodDef`または`mdMemberRef`に実装されているインターフェイス メソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="03792-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03792-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="03792-109">Requirements</span></span>  
 <span data-ttu-id="03792-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03792-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03792-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03792-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03792-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="03792-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03792-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03792-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03792-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="03792-114">See also</span></span>

- [<span data-ttu-id="03792-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03792-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="03792-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03792-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
