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
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008756"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="e10b0-102">IMetaDataEmit::SetEventProps メソッド</span><span class="sxs-lookup"><span data-stu-id="e10b0-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="e10b0-103">[IMetaDataEmit::D efineEvent](imetadataemit-defineevent-method.md)の前の呼び出しで定義されたイベントの指定された機能を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="e10b0-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e10b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e10b0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e10b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e10b0-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="e10b0-106">からイベントトークン。</span><span class="sxs-lookup"><span data-stu-id="e10b0-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="e10b0-107">からイベントフラグ。</span><span class="sxs-lookup"><span data-stu-id="e10b0-107">[in] Event flags.</span></span> <span data-ttu-id="e10b0-108">これは、値のビットマスクです `CorEventAttr` 。</span><span class="sxs-lookup"><span data-stu-id="e10b0-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="e10b0-109">からイベントクラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="e10b0-109">[in] The token for the event class.</span></span> <span data-ttu-id="e10b0-110">これは、 `mdTypeDef` またはトークンのいずれか `mdTypeRef` です。</span><span class="sxs-lookup"><span data-stu-id="e10b0-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="e10b0-111">からイベントの定期受信に使用するメソッド、または null。</span><span class="sxs-lookup"><span data-stu-id="e10b0-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="e10b0-112">からイベントのサブスクリプションを解除するために使用するメソッド、または null。</span><span class="sxs-lookup"><span data-stu-id="e10b0-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="e10b0-113">からイベントを発生させるために (派生クラスによって) 使用されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="e10b0-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="e10b0-114">からイベントに関連付けられている他のメソッドのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="e10b0-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="e10b0-115">配列の最後の要素は、である必要があり `mdMethodDefNil` ます。</span><span class="sxs-lookup"><span data-stu-id="e10b0-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e10b0-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="e10b0-116">Requirements</span></span>  
 <span data-ttu-id="e10b0-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e10b0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e10b0-118">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e10b0-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e10b0-119">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e10b0-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e10b0-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e10b0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10b0-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e10b0-121">See also</span></span>

- [<span data-ttu-id="e10b0-122">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e10b0-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e10b0-123">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e10b0-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
