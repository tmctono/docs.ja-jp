---
title: IMetaDataImport::EnumTypeSpecs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01151dc2fe6aa995285a34076527609816b2f3e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753622"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="c47c8-102">IMetaDataImport::EnumTypeSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="c47c8-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="c47c8-103">現在のメタデータ スコープに定義されている TypeSpec トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c47c8-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c47c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="c47c8-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c47c8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c47c8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c47c8-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c47c8-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c47c8-107">この値では、このメソッドの最初の呼び出しは、NULL にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47c8-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="c47c8-108">[out]TypeSpec トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="c47c8-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c47c8-109">[in] `rTypeSpecs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c47c8-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="c47c8-110">[out]返される TypeSpec トークン数`rTypeSpecs`します。</span><span class="sxs-lookup"><span data-stu-id="c47c8-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c47c8-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c47c8-111">Return Value</span></span>  
  
|<span data-ttu-id="c47c8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c47c8-112">HRESULT</span></span>|<span data-ttu-id="c47c8-113">説明</span><span class="sxs-lookup"><span data-stu-id="c47c8-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c47c8-114">`EnumTypeSpecs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c47c8-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c47c8-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="c47c8-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c47c8-116">その場合は、`pcTypeSpecs`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="c47c8-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c47c8-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="c47c8-117">Remarks</span></span>  
 <span data-ttu-id="c47c8-118">TypeSpec トークンがによって作成された、 [imetadataemit::gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c47c8-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c47c8-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="c47c8-119">Requirements</span></span>  
 <span data-ttu-id="c47c8-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c47c8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c47c8-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c47c8-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c47c8-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c47c8-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c47c8-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c47c8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c47c8-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c47c8-124">See also</span></span>

- [<span data-ttu-id="c47c8-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c47c8-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c47c8-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c47c8-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
