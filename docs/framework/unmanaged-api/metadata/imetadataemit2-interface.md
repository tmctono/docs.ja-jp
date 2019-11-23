---
title: IMetaDataEmit2 インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447918"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="1b26d-102">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b26d-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="1b26d-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span><span class="sxs-lookup"><span data-stu-id="1b26d-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b26d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-104">Methods</span></span>  
  
|<span data-ttu-id="1b26d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-105">Method</span></span>|<span data-ttu-id="1b26d-106">説明</span><span class="sxs-lookup"><span data-stu-id="1b26d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b26d-107">DefineGenericParam メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="1b26d-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span><span class="sxs-lookup"><span data-stu-id="1b26d-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="1b26d-109">DefineMethodSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="1b26d-110">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="1b26d-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="1b26d-111">GetDeltaSaveSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="1b26d-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span><span class="sxs-lookup"><span data-stu-id="1b26d-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="1b26d-113">ResetENCLog メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="1b26d-114">Resets the edit-and-continue log and starts a new session.</span><span class="sxs-lookup"><span data-stu-id="1b26d-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="1b26d-115">SaveDelta メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="1b26d-116">Saves changes from the current edit-and-continue session to the specified file.</span><span class="sxs-lookup"><span data-stu-id="1b26d-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="1b26d-117">SaveDeltaToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="1b26d-118">Saves changes from the current edit-and-continue session to memory.</span><span class="sxs-lookup"><span data-stu-id="1b26d-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="1b26d-119">SaveDeltaToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="1b26d-120">Saves changes from the current edit-and-continue session to the specified stream.</span><span class="sxs-lookup"><span data-stu-id="1b26d-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="1b26d-121">SetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="1b26d-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="1b26d-122">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="1b26d-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b26d-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="1b26d-123">Requirements</span></span>  
 <span data-ttu-id="1b26d-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b26d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b26d-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1b26d-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b26d-126">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b26d-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b26d-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b26d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b26d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b26d-128">See also</span></span>

- [<span data-ttu-id="1b26d-129">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b26d-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="1b26d-130">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b26d-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
