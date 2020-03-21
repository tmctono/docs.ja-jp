---
title: IMetaDataEmit::DefineCustomAttribute メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 9c4ed282e259aa46fc0cb0175214dc51d3d5fbee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175890"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="36c8f-102">IMetaDataEmit::DefineCustomAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="36c8f-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="36c8f-103">指定したメタデータ シグネチャを持つカスタム属性の定義を作成し、指定したオブジェクトにアタッチし、そのカスタム属性定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="36c8f-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="36c8f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c8f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36c8f-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="36c8f-106">[in]所有者アイテムのトークン。</span><span class="sxs-lookup"><span data-stu-id="36c8f-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="36c8f-107">[in]カスタム属性を識別するトークン。</span><span class="sxs-lookup"><span data-stu-id="36c8f-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="36c8f-108">[in]カスタム属性へのポインター。</span><span class="sxs-lookup"><span data-stu-id="36c8f-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="36c8f-109">[in]のバイト数`pCustomAttribute`。</span><span class="sxs-lookup"><span data-stu-id="36c8f-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="36c8f-110">[アウト]割`mdCustomAttribute`り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="36c8f-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c8f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="36c8f-111">Requirements</span></span>  
 <span data-ttu-id="36c8f-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c8f-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="36c8f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36c8f-114">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="36c8f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36c8f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c8f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="36c8f-116">See also</span></span>

- [<span data-ttu-id="36c8f-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c8f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="36c8f-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36c8f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
