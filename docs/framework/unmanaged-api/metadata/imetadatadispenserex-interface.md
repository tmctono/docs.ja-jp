---
title: IMetaDataDispenserEx インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 985cdea670714394119fb846e9e55a01713559a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431144"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="319a6-102">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="319a6-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="319a6-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="319a6-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="319a6-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-104">Methods</span></span>  
  
|<span data-ttu-id="319a6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-105">Method</span></span>|<span data-ttu-id="319a6-106">説明</span><span class="sxs-lookup"><span data-stu-id="319a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="319a6-107">FindAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="319a6-108">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="319a6-108">This method is not implemented.</span></span> <span data-ttu-id="319a6-109">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="319a6-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="319a6-110">FindAssemblyModule メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="319a6-111">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="319a6-111">This method is not implemented.</span></span> <span data-ttu-id="319a6-112">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="319a6-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="319a6-113">GetCORSystemDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="319a6-114">Gets the directory that holds the current common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="319a6-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="319a6-115">This method is supported only for use by out-of-process debuggers.</span><span class="sxs-lookup"><span data-stu-id="319a6-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="319a6-116">If called from another component, it will return E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="319a6-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="319a6-117">GetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="319a6-118">Gets the value of the specified option for the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="319a6-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="319a6-119">The option controls how calls to the current metadata scope are handled.</span><span class="sxs-lookup"><span data-stu-id="319a6-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="319a6-120">OpenScopeOnITypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="319a6-121">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="319a6-121">This method is not implemented.</span></span> <span data-ttu-id="319a6-122">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="319a6-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="319a6-123">SetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="319a6-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="319a6-124">Sets the specified option to a given value for the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="319a6-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="319a6-125">The option controls how calls to the current metadata scope are handled.</span><span class="sxs-lookup"><span data-stu-id="319a6-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="319a6-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="319a6-126">Requirements</span></span>  
 <span data-ttu-id="319a6-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="319a6-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="319a6-128">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="319a6-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="319a6-129">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="319a6-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="319a6-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="319a6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319a6-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="319a6-131">See also</span></span>

- [<span data-ttu-id="319a6-132">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="319a6-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="319a6-133">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="319a6-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="319a6-134">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="319a6-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="319a6-135">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="319a6-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
