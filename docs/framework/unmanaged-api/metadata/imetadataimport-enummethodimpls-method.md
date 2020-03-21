---
title: IMetaDataImport::EnumMethodImpls メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175474"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="27992-102">IMetaDataImport::EnumMethodImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="27992-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="27992-103">指定した型のメソッドを表す MethodBody トークンと MethodDeclaration トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="27992-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27992-104">構文</span><span class="sxs-lookup"><span data-stu-id="27992-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27992-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27992-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="27992-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="27992-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="27992-107">このメソッドの最初の呼び出しでは、NULL にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27992-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="27992-108">[in]列挙するメソッドの実装を持つ型の TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="27992-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="27992-109">[アウト]メソッドボディ トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="27992-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="27992-110">[アウト]メソッド宣言トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="27992-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="27992-111">[in]配列と`rMethodBody``rMethodDecl`配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="27992-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="27992-112">[in]で返されるメソッドの実際の`rMethodBody`数`rMethodDecl`と で返されるメソッドの実際の数。</span><span class="sxs-lookup"><span data-stu-id="27992-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27992-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="27992-113">Return Value</span></span>  
  
|<span data-ttu-id="27992-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27992-114">HRESULT</span></span>|<span data-ttu-id="27992-115">説明</span><span class="sxs-lookup"><span data-stu-id="27992-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="27992-116">`EnumMethodImpls`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="27992-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="27992-117">列挙するメソッド トークンがありません。</span><span class="sxs-lookup"><span data-stu-id="27992-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="27992-118">その場合は、`pcTokens`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="27992-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27992-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="27992-119">Requirements</span></span>  
 <span data-ttu-id="27992-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27992-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27992-121">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="27992-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27992-122">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="27992-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27992-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27992-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27992-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="27992-124">See also</span></span>

- [<span data-ttu-id="27992-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27992-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="27992-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27992-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
