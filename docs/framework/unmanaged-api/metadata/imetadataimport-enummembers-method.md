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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50035799fcfa4c4b08404d63fe91e7dba85722fa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758839"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="5add2-102">IMetaDataImport::EnumMembers メソッド</span><span class="sxs-lookup"><span data-stu-id="5add2-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="5add2-103">指定した型のメンバーを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="5add2-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5add2-104">構文</span><span class="sxs-lookup"><span data-stu-id="5add2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5add2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5add2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5add2-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5add2-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="5add2-107">[in]そのメンバーが列挙型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="5add2-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="5add2-108">[out]MemberDef トークンを保持するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="5add2-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5add2-109">[in] `rMembers` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="5add2-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5add2-110">[out]実際に返される MemberDef トークン数`rMembers`します。</span><span class="sxs-lookup"><span data-stu-id="5add2-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5add2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="5add2-111">Return Value</span></span>  
  
|<span data-ttu-id="5add2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5add2-112">HRESULT</span></span>|<span data-ttu-id="5add2-113">説明</span><span class="sxs-lookup"><span data-stu-id="5add2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5add2-114">`EnumMembers` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="5add2-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5add2-115">MemberDef トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="5add2-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="5add2-116">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="5add2-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5add2-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="5add2-117">Remarks</span></span>  
 <span data-ttu-id="5add2-118">クラスのメンバーのコレクションを列挙する場合、`EnumMembers`メンバーのみを返します (フィールドおよびメソッドが**いない**プロパティまたはイベント)、クラスで直接定義されています。</span><span class="sxs-lookup"><span data-stu-id="5add2-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="5add2-119">クラスは、継承されたメンバーの実装を提供する場合でも、クラスが継承する任意のメンバーは返されません。</span><span class="sxs-lookup"><span data-stu-id="5add2-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="5add2-120">継承されたメンバーを列挙するために、呼び出し元は明示的に継承チェーンを走査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5add2-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="5add2-121">継承チェーンの規則は、言語や、元のメタデータを生成するコンパイラによって異なる場合がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5add2-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="5add2-122">プロパティおよびイベントはによって列挙されない`EnumMembers`します。</span><span class="sxs-lookup"><span data-stu-id="5add2-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="5add2-123">使用して、それらを列挙する[EnumProperties](imetadataimport-enumproperties-method.md)または[EnumEvents](imetadataimport-enumevents-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="5add2-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="5add2-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="5add2-124">Requirements</span></span>  
 <span data-ttu-id="5add2-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5add2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5add2-126">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5add2-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5add2-127">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5add2-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5add2-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5add2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5add2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5add2-129">See also</span></span>

- [<span data-ttu-id="5add2-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5add2-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5add2-131">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5add2-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
