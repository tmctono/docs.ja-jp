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
ms.openlocfilehash: 743b6bed1a5d62f5214b8366b1a3c6e4ebecb98b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441717"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="e5f95-102">IMetaDataImport::EnumMemberRefs メソッド</span><span class="sxs-lookup"><span data-stu-id="e5f95-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="e5f95-103">指定した型のメンバーを表す MemberRef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="e5f95-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f95-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5f95-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f95-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5f95-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e5f95-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5f95-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="e5f95-107">からメンバーを列挙する型の TypeDef、TypeRef、MethodDef、または ModuleRef トークン。</span><span class="sxs-lookup"><span data-stu-id="e5f95-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="e5f95-108">入出力MemberRef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="e5f95-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e5f95-109">[in] `rMemberRefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="e5f95-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e5f95-110">入出力`rMemberRefs`で返された MemberRef トークンの実際の数。</span><span class="sxs-lookup"><span data-stu-id="e5f95-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5f95-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e5f95-111">Return Value</span></span>  
  
|<span data-ttu-id="e5f95-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5f95-112">HRESULT</span></span>|<span data-ttu-id="e5f95-113">説明</span><span class="sxs-lookup"><span data-stu-id="e5f95-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e5f95-114">`EnumMemberRefs` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e5f95-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e5f95-115">列挙する MemberRef トークンがありません。</span><span class="sxs-lookup"><span data-stu-id="e5f95-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="e5f95-116">この場合、`pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="e5f95-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5f95-117">要件</span><span class="sxs-lookup"><span data-stu-id="e5f95-117">Requirements</span></span>  
 <span data-ttu-id="e5f95-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f95-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f95-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e5f95-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5f95-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e5f95-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5f95-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f95-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f95-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5f95-122">See also</span></span>

- [<span data-ttu-id="e5f95-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5f95-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e5f95-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5f95-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
