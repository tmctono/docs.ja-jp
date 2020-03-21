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
ms.openlocfilehash: 64d76efa8c2f29fda559e5c84217b865540027ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175825"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="eb3fc-102">IMetaDataEmit::DefineMethodImpl メソッド</span><span class="sxs-lookup"><span data-stu-id="eb3fc-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="eb3fc-103">インターフェイスから継承されたメソッドの実装の定義を作成し、そのメソッド実装定義にトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb3fc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb3fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb3fc-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="eb3fc-106">[in]実装`mdTypedef`クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="eb3fc-107">[in]コード`mdMethodDef`本体`mdMemberRef`の トークンまたはトークン。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="eb3fc-108">[in]実装`mdMethodDef`される`mdMemberRef`インターフェイス メソッドのトークンまたはトークン。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb3fc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="eb3fc-109">Requirements</span></span>  
 <span data-ttu-id="eb3fc-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb3fc-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="eb3fc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb3fc-112">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fc-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb3fc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb3fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3fc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb3fc-114">See also</span></span>

- [<span data-ttu-id="eb3fc-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb3fc-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="eb3fc-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb3fc-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
