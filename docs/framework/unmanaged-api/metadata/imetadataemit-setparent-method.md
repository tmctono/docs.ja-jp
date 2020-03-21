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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175604"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="0d153-102">IMetaDataEmit::SetParent メソッド</span><span class="sxs-lookup"><span data-stu-id="0d153-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="0d153-103">指定したメンバーが[、IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)への以前の呼び出しによって定義された[:D](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)メンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d153-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d153-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d153-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d153-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d153-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="0d153-106">[in]新`mdMemberRef`しい親を受け取るトークン。</span><span class="sxs-lookup"><span data-stu-id="0d153-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="0d153-107">[in]新`mdToken`しい親の場合。</span><span class="sxs-lookup"><span data-stu-id="0d153-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d153-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d153-108">Requirements</span></span>  
 <span data-ttu-id="0d153-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d153-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d153-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="0d153-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d153-111">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d153-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d153-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d153-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d153-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d153-113">See also</span></span>

- [<span data-ttu-id="0d153-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d153-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0d153-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d153-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
