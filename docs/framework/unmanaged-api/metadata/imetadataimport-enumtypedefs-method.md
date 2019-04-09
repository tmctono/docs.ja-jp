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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103364"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="90c3e-102">IMetaDataImport::EnumTypeDefs メソッド</span><span class="sxs-lookup"><span data-stu-id="90c3e-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="90c3e-103">現在のスコープ内のすべての型を表す TypeDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="90c3e-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c3e-104">構文</span><span class="sxs-lookup"><span data-stu-id="90c3e-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90c3e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90c3e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="90c3e-106">[out]新しい列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="90c3e-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="90c3e-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="90c3e-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="90c3e-108">[in]TypeDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="90c3e-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="90c3e-109">[in] `rTypeDefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="90c3e-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="90c3e-110">[out]TypeDef のトークンで返される数`rTypeDefs`します。</span><span class="sxs-lookup"><span data-stu-id="90c3e-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90c3e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="90c3e-111">Return Value</span></span>  
  
|<span data-ttu-id="90c3e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90c3e-112">HRESULT</span></span>|<span data-ttu-id="90c3e-113">説明</span><span class="sxs-lookup"><span data-stu-id="90c3e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` <span data-ttu-id="90c3e-114">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="90c3e-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="90c3e-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="90c3e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="90c3e-116">その場合は、`pcTypeDefs`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="90c3e-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90c3e-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="90c3e-117">Remarks</span></span>  
 <span data-ttu-id="90c3e-118">TypeDef トークンは、クラスやインターフェイスなどの型だけでなく、機能拡張メカニズムを使用して追加された型を表します。</span><span class="sxs-lookup"><span data-stu-id="90c3e-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c3e-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="90c3e-119">Requirements</span></span>  
 <span data-ttu-id="90c3e-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c3e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c3e-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90c3e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90c3e-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="90c3e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="90c3e-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="90c3e-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="90c3e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="90c3e-124">See also</span></span>

- [<span data-ttu-id="90c3e-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90c3e-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="90c3e-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90c3e-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
