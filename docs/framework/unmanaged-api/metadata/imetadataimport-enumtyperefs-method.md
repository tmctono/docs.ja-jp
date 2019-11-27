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
ms.openlocfilehash: 778ebf1d4fad0c8703964be88fdc3ff8c033bc28
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449985"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="cbea1-102">IMetaDataImport::EnumTypeRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="cbea1-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="cbea1-103">現在のメタデータ スコープに定義されている TypeRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbea1-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbea1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbea1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbea1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cbea1-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cbea1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cbea1-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="cbea1-108">入出力TypeRef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="cbea1-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cbea1-109">[in] `rTypeRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="cbea1-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="cbea1-110">入出力`rTypeRefs`で返された TypeRef トークンの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cbea1-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbea1-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="cbea1-111">Return Value</span></span>  
  
|<span data-ttu-id="cbea1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cbea1-112">HRESULT</span></span>|<span data-ttu-id="cbea1-113">説明</span><span class="sxs-lookup"><span data-stu-id="cbea1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cbea1-114">`EnumTypeRefs` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="cbea1-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cbea1-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="cbea1-116">この場合、`pcTypeRefs` は0になります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbea1-117">コメント</span><span class="sxs-lookup"><span data-stu-id="cbea1-117">Remarks</span></span>  
 <span data-ttu-id="cbea1-118">TypeRef トークンは、型への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbea1-119">要件</span><span class="sxs-lookup"><span data-stu-id="cbea1-119">Requirements</span></span>  
 <span data-ttu-id="cbea1-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbea1-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="cbea1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbea1-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="cbea1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbea1-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbea1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbea1-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbea1-124">See also</span></span>

- [<span data-ttu-id="cbea1-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbea1-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cbea1-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbea1-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
