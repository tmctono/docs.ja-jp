---
title: IMetaDataEmit::SetEventProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177528"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="27c1a-102">IMetaDataEmit::SetEventProps メソッド</span><span class="sxs-lookup"><span data-stu-id="27c1a-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="27c1a-103">[IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)への以前の呼び出しによって定義されたイベントの指定された機能を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="27c1a-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c1a-104">構文</span><span class="sxs-lookup"><span data-stu-id="27c1a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27c1a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27c1a-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="27c1a-106">[in]イベント トークン。</span><span class="sxs-lookup"><span data-stu-id="27c1a-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="27c1a-107">[in]イベント フラグ。</span><span class="sxs-lookup"><span data-stu-id="27c1a-107">[in] Event flags.</span></span> <span data-ttu-id="27c1a-108">これは値の`CorEventAttr`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="27c1a-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="27c1a-109">[in]イベント クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="27c1a-109">[in] The token for the event class.</span></span> <span data-ttu-id="27c1a-110">これは、トークン`mdTypeDef`またはトークンのいずれか`mdTypeRef`です。</span><span class="sxs-lookup"><span data-stu-id="27c1a-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="27c1a-111">[in]イベントをサブスクライブするために使用するメソッド、または null。</span><span class="sxs-lookup"><span data-stu-id="27c1a-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="27c1a-112">[in]イベントのサブスクライブを解除するために使用するメソッド、または null。</span><span class="sxs-lookup"><span data-stu-id="27c1a-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="27c1a-113">[in]イベントを発生させるために (派生クラスによって) 使用されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="27c1a-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="27c1a-114">[in]イベントに関連付けられている他のメソッドのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="27c1a-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="27c1a-115">配列の最後の要素は`mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="27c1a-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27c1a-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="27c1a-116">Requirements</span></span>  
 <span data-ttu-id="27c1a-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c1a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27c1a-118">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="27c1a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27c1a-119">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="27c1a-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27c1a-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27c1a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c1a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="27c1a-121">See also</span></span>

- [<span data-ttu-id="27c1a-122">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27c1a-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="27c1a-123">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27c1a-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
