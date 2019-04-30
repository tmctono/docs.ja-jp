---
title: IMetaDataImport::EnumMemberRefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08577f15a6fab0e630d40032a23c273ee935faa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992330"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="c98f6-102">IMetaDataImport::EnumMemberRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="c98f6-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="c98f6-103">指定した型のメンバーを表す MemberRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c98f6-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c98f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="c98f6-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c98f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c98f6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c98f6-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c98f6-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="c98f6-107">[in]そのメンバーが列挙型の TypeDef、TypeRef、MethodDef、または ModuleRef トークンです。</span><span class="sxs-lookup"><span data-stu-id="c98f6-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="c98f6-108">[out]MemberRef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="c98f6-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c98f6-109">[in] `rMemberRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c98f6-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c98f6-110">[out]実際に返される MemberRef トークン数`rMemberRefs`します。</span><span class="sxs-lookup"><span data-stu-id="c98f6-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c98f6-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c98f6-111">Return Value</span></span>  
  
|<span data-ttu-id="c98f6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c98f6-112">HRESULT</span></span>|<span data-ttu-id="c98f6-113">説明</span><span class="sxs-lookup"><span data-stu-id="c98f6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c98f6-114">`EnumMemberRefs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c98f6-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c98f6-115">MemberRef トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="c98f6-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="c98f6-116">その場合は、`pcTokens`は 0 にします。</span><span class="sxs-lookup"><span data-stu-id="c98f6-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c98f6-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="c98f6-117">Requirements</span></span>  
 <span data-ttu-id="c98f6-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c98f6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c98f6-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c98f6-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c98f6-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c98f6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c98f6-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c98f6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c98f6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c98f6-122">See also</span></span>

- [<span data-ttu-id="c98f6-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c98f6-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c98f6-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c98f6-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
