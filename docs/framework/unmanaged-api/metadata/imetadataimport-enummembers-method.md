---
title: IMetaDataImport::EnumMembers メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175487"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="666b3-102">IMetaDataImport::EnumMembers メソッド</span><span class="sxs-lookup"><span data-stu-id="666b3-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="666b3-103">指定した型のメンバーを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="666b3-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="666b3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="666b3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="666b3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="666b3-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="666b3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="666b3-107">[in]列挙されるメンバーを持つ型を表す TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="666b3-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="666b3-108">[アウト]MemberDef トークンを保持するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="666b3-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="666b3-109">[in] `rMembers` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="666b3-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="666b3-110">[アウト]に返される MemberDef トークンの`rMembers`実際の数。</span><span class="sxs-lookup"><span data-stu-id="666b3-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="666b3-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="666b3-111">Return Value</span></span>  
  
|<span data-ttu-id="666b3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="666b3-112">HRESULT</span></span>|<span data-ttu-id="666b3-113">説明</span><span class="sxs-lookup"><span data-stu-id="666b3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="666b3-114">`EnumMembers`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="666b3-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="666b3-115">列挙する MemberDef トークンがありません。</span><span class="sxs-lookup"><span data-stu-id="666b3-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="666b3-116">その場合は、`pcTokens`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="666b3-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="666b3-117">解説</span><span class="sxs-lookup"><span data-stu-id="666b3-117">Remarks</span></span>  
 <span data-ttu-id="666b3-118">クラスのメンバーのコレクションを列挙する場合、`EnumMembers`クラスに直接定義されたメンバー (フィールドとメソッド**not**ではなく、プロパティまたはイベント) のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="666b3-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="666b3-119">クラスが継承されたメンバーの実装を提供する場合でも、クラスが継承するメンバーは返しません。</span><span class="sxs-lookup"><span data-stu-id="666b3-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="666b3-120">継承されたメンバーを列挙するには、呼び出し元が継承チェーンを明示的にウォークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="666b3-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="666b3-121">継承チェーンの規則は、元のメタデータを出力した言語またはコンパイラによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="666b3-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="666b3-122">プロパティとイベントは、 によって`EnumMembers`列挙されません。</span><span class="sxs-lookup"><span data-stu-id="666b3-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="666b3-123">これらのプロパティを列挙するには、[列挙プロパティ](imetadataimport-enumproperties-method.md)または[列挙イベント](imetadataimport-enumevents-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="666b3-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="666b3-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="666b3-124">Requirements</span></span>  
 <span data-ttu-id="666b3-125">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="666b3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666b3-126">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="666b3-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="666b3-127">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="666b3-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="666b3-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666b3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666b3-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="666b3-129">See also</span></span>

- [<span data-ttu-id="666b3-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="666b3-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="666b3-131">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="666b3-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
