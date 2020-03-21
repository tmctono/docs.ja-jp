---
title: IMetaDataImport::EnumTypeRefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175435"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="e87e2-102">IMetaDataImport::EnumTypeRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="e87e2-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="e87e2-103">現在のメタデータ スコープに定義されている TypeRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="e87e2-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e87e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="e87e2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e87e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e87e2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e87e2-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e87e2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e87e2-107">このメソッドの最初の呼び出しでは、NULL にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e87e2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="e87e2-108">[アウト]TypeRef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="e87e2-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e87e2-109">[in] `rTypeRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="e87e2-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="e87e2-110">[アウト]に返される TypeRef トークンの数への`rTypeRefs`ポインター。</span><span class="sxs-lookup"><span data-stu-id="e87e2-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e87e2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e87e2-111">Return Value</span></span>  
  
|<span data-ttu-id="e87e2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e87e2-112">HRESULT</span></span>|<span data-ttu-id="e87e2-113">説明</span><span class="sxs-lookup"><span data-stu-id="e87e2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e87e2-114">`EnumTypeRefs`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e87e2-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e87e2-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="e87e2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e87e2-116">その場合は、`pcTypeRefs`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="e87e2-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e87e2-117">解説</span><span class="sxs-lookup"><span data-stu-id="e87e2-117">Remarks</span></span>  
 <span data-ttu-id="e87e2-118">TypeRef トークンは、型への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="e87e2-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e87e2-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="e87e2-119">Requirements</span></span>  
 <span data-ttu-id="e87e2-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e87e2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e87e2-121">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e87e2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e87e2-122">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="e87e2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e87e2-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e87e2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e87e2-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e87e2-124">See also</span></span>

- [<span data-ttu-id="e87e2-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e87e2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e87e2-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e87e2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
