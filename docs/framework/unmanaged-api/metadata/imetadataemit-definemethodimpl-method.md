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
ms.openlocfilehash: 5ed5afbbf49b6680d00e78b6af3d45c6f0a7229d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004492"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="58309-102">IMetaDataEmit::DefineMethodImpl メソッド</span><span class="sxs-lookup"><span data-stu-id="58309-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="58309-103">インターフェイスから継承されたメソッドの実装の定義を作成し、そのメソッド実装定義にトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="58309-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58309-104">構文</span><span class="sxs-lookup"><span data-stu-id="58309-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58309-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58309-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="58309-106">から`mdTypedef`実装するクラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="58309-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="58309-107">から`mdMethodDef` `mdMemberRef` コード本体のまたはトークン。</span><span class="sxs-lookup"><span data-stu-id="58309-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="58309-108">から`mdMethodDef` `mdMemberRef` 実装されているインターフェイスメソッドのまたはトークン。</span><span class="sxs-lookup"><span data-stu-id="58309-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58309-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="58309-109">Requirements</span></span>  
 <span data-ttu-id="58309-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58309-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58309-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="58309-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58309-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="58309-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58309-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58309-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58309-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="58309-114">See also</span></span>

- [<span data-ttu-id="58309-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58309-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="58309-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58309-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
