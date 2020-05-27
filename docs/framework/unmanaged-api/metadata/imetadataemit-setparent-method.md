---
title: IMetaDataEmit::SetParent メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: da82950ea1a0da81c77d173be9ab45dcb3001bfe
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007833"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="ed513-102">IMetaDataEmit::SetParent メソッド</span><span class="sxs-lookup"><span data-stu-id="ed513-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="ed513-103">前の[IMetaDataEmit::D efineTypeDef](imetadataemit-definetypedef-method.md)の呼び出しで定義されているように、 [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)の前の呼び出しで定義されている指定されたメンバーが、指定された型のメンバーであることを確立します。</span><span class="sxs-lookup"><span data-stu-id="ed513-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed513-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed513-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed513-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed513-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="ed513-106">から`mdMemberRef`新しい親を受け取るトークン。</span><span class="sxs-lookup"><span data-stu-id="ed513-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="ed513-107">から`mdToken`新しい親の。</span><span class="sxs-lookup"><span data-stu-id="ed513-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed513-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ed513-108">Requirements</span></span>  
 <span data-ttu-id="ed513-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed513-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed513-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ed513-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed513-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed513-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed513-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed513-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed513-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed513-113">See also</span></span>

- [<span data-ttu-id="ed513-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed513-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ed513-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ed513-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
