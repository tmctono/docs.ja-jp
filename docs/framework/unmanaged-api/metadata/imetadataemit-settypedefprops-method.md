---
title: IMetaDataEmit::SetTypeDefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447716"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="27196-102">IMetaDataEmit::SetTypeDefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="27196-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="27196-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="27196-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27196-104">構文</span><span class="sxs-lookup"><span data-stu-id="27196-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27196-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27196-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="27196-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="27196-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="27196-107">[in] `TypeDef` attributes.</span><span class="sxs-lookup"><span data-stu-id="27196-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="27196-108">This is a bitmask of `CorTypeAttr` values.</span><span class="sxs-lookup"><span data-stu-id="27196-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="27196-109">[in] The `mdToken` of the base class.</span><span class="sxs-lookup"><span data-stu-id="27196-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="27196-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span><span class="sxs-lookup"><span data-stu-id="27196-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="27196-111">[in] An array of tokens for the interfaces that this type implements.</span><span class="sxs-lookup"><span data-stu-id="27196-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="27196-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="27196-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="27196-113">The last element of the array is must be `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="27196-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27196-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="27196-114">Requirements</span></span>  
 <span data-ttu-id="27196-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27196-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27196-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27196-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27196-117">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27196-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27196-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27196-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27196-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="27196-119">See also</span></span>

- [<span data-ttu-id="27196-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27196-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="27196-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27196-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
