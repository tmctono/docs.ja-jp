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
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="b2d97-102">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d97-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="b2d97-103">[IMetaDataDispenser インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)インターフェイスを拡張して、メタデータ api が現在のメタデータスコープに対してどのように動作するかを制御する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2d97-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-104">Methods</span></span>  
  
|<span data-ttu-id="b2d97-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-105">Method</span></span>|<span data-ttu-id="b2d97-106">説明</span><span class="sxs-lookup"><span data-stu-id="b2d97-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2d97-107">FindAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="b2d97-108">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="b2d97-108">This method is not implemented.</span></span> <span data-ttu-id="b2d97-109">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b2d97-110">FindAssemblyModule メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="b2d97-111">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="b2d97-111">This method is not implemented.</span></span> <span data-ttu-id="b2d97-112">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b2d97-113">GetCORSystemDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="b2d97-114">現在の共通言語ランタイム (CLR) が格納されているディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="b2d97-115">このメソッドは、アウトプロセスデバッガーでの使用に対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b2d97-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="b2d97-116">別のコンポーネントから呼び出された場合は、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b2d97-117">GetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="b2d97-118">現在のメタデータスコープの指定したオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="b2d97-119">オプションは、現在のメタデータスコープへの呼び出しの処理方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="b2d97-120">OpenScopeOnITypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="b2d97-121">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="b2d97-121">This method is not implemented.</span></span> <span data-ttu-id="b2d97-122">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b2d97-123">SetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="b2d97-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="b2d97-124">指定されたオプションを、現在のメタデータスコープの指定された値に設定します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="b2d97-125">オプションは、現在のメタデータスコープへの呼び出しの処理方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="b2d97-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2d97-126">要件</span><span class="sxs-lookup"><span data-stu-id="b2d97-126">Requirements</span></span>  
 <span data-ttu-id="b2d97-127">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2d97-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2d97-128">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="b2d97-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2d97-129">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b2d97-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2d97-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2d97-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d97-131">参照</span><span class="sxs-lookup"><span data-stu-id="b2d97-131">See also</span></span>

- [<span data-ttu-id="b2d97-132">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d97-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b2d97-133">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d97-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="b2d97-134">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d97-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b2d97-135">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2d97-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
