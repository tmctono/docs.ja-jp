---
title: IMetaDataEmit::DefineEvent メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175851"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="6a791-102">IMetaDataEmit::DefineEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="6a791-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="6a791-103">指定したメタデータ シグネチャを持つイベントの定義を作成し、そのイベント定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a791-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a791-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a791-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a791-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a791-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6a791-106">[in]ターゲット クラスまたはインターフェイスのトークン。</span><span class="sxs-lookup"><span data-stu-id="6a791-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="6a791-107">これは、`mdTypeDef`トークンまたは`mdTypeDefNil`トークンです。</span><span class="sxs-lookup"><span data-stu-id="6a791-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="6a791-108">[in]イベントの名前。</span><span class="sxs-lookup"><span data-stu-id="6a791-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="6a791-109">[in]イベント フラグ。</span><span class="sxs-lookup"><span data-stu-id="6a791-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="6a791-110">[in]イベント クラスのトークン。</span><span class="sxs-lookup"><span data-stu-id="6a791-110">[in] The token for the event class.</span></span> <span data-ttu-id="6a791-111">これは`mdTypeDef`、 、または`mdTypeRef`トークンです`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="6a791-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="6a791-112">[in]イベントをサブスクライブするために使用するメソッド、または null。</span><span class="sxs-lookup"><span data-stu-id="6a791-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="6a791-113">[in]イベントのサブスクライブを解除するために使用するメソッド、または null。</span><span class="sxs-lookup"><span data-stu-id="6a791-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="6a791-114">[in]イベントを発生させるために (派生クラスによって) 使用されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="6a791-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="6a791-115">[in]イベントに関連付けられている他のメソッドのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="6a791-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="6a791-116">配列は`mdMethodDefNil`トークンで終了します。</span><span class="sxs-lookup"><span data-stu-id="6a791-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="6a791-117">[アウト]イベントに割り当てられたメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="6a791-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a791-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a791-118">Requirements</span></span>  
 <span data-ttu-id="6a791-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a791-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a791-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="6a791-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a791-121">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a791-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a791-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a791-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a791-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a791-123">See also</span></span>

- [<span data-ttu-id="6a791-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a791-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6a791-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a791-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
