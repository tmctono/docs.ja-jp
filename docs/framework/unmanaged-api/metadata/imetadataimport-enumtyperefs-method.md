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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65dbbeb76c1f31044fddf6df69c4daf63617c079
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480391"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="7b69e-102">IMetaDataImport::EnumTypeRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="7b69e-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="7b69e-103">現在のメタデータ スコープに定義されている TypeRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="7b69e-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b69e-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b69e-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b69e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b69e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7b69e-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7b69e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7b69e-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="7b69e-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="7b69e-108">[out]TypeRef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="7b69e-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7b69e-109">[in] `rTypeRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="7b69e-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="7b69e-110">[out]返される TypeRef トークンの数へのポインター`rTypeRefs`します。</span><span class="sxs-lookup"><span data-stu-id="7b69e-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b69e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="7b69e-111">Return Value</span></span>  
  
|<span data-ttu-id="7b69e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b69e-112">HRESULT</span></span>|<span data-ttu-id="7b69e-113">説明</span><span class="sxs-lookup"><span data-stu-id="7b69e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7b69e-114">`EnumTypeRefs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="7b69e-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7b69e-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="7b69e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7b69e-116">その場合は、`pcTypeRefs`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="7b69e-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b69e-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b69e-117">Remarks</span></span>  
 <span data-ttu-id="7b69e-118">TypeRef トークンは、型への参照を表します。</span><span class="sxs-lookup"><span data-stu-id="7b69e-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b69e-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b69e-119">Requirements</span></span>  
 <span data-ttu-id="7b69e-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b69e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b69e-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b69e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b69e-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7b69e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b69e-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b69e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b69e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b69e-124">See also</span></span>
- [<span data-ttu-id="7b69e-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b69e-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7b69e-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b69e-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
