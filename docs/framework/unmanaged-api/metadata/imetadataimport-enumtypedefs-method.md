---
title: IMetaDataImport::EnumTypeDefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 20913d1cfa258036e8c20e826415f96a8984fdb4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103364"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="d5ecf-102">IMetaDataImport::EnumTypeDefs メソッド</span><span class="sxs-lookup"><span data-stu-id="d5ecf-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="d5ecf-103">現在のスコープ内のすべての型を表す TypeDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ecf-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5ecf-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5ecf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5ecf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d5ecf-106">[out]新しい列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="d5ecf-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="d5ecf-108">[in]TypeDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d5ecf-109">[in] `rTypeDefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="d5ecf-110">[out]TypeDef のトークンで返される数`rTypeDefs`します。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5ecf-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d5ecf-111">Return Value</span></span>  
  
|<span data-ttu-id="d5ecf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5ecf-112">HRESULT</span></span>|<span data-ttu-id="d5ecf-113">説明</span><span class="sxs-lookup"><span data-stu-id="d5ecf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d5ecf-114">`EnumTypeDefs` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d5ecf-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d5ecf-116">その場合は、`pcTypeDefs`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5ecf-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5ecf-117">Remarks</span></span>  
 <span data-ttu-id="d5ecf-118">TypeDef トークンは、クラスやインターフェイスなどの型だけでなく、機能拡張メカニズムを使用して追加された型を表します。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ecf-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5ecf-119">Requirements</span></span>  
 <span data-ttu-id="d5ecf-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ecf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ecf-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5ecf-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5ecf-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d5ecf-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5ecf-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ecf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ecf-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5ecf-124">See also</span></span>

- [<span data-ttu-id="d5ecf-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5ecf-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d5ecf-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5ecf-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
