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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8be30e8c3b6bc7c03ede5f897f176e04153003b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781974"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="a73f2-102">IMetaDataImport::EnumMethodImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="a73f2-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="a73f2-103">指定した型のメソッドを表す MethodBody トークンと MethodDeclaration トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="a73f2-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a73f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="a73f2-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a73f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a73f2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a73f2-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a73f2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a73f2-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="a73f2-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="a73f2-108">[in]TypeDef は、列挙するためにそのメソッドの実装の種類のトークンします。</span><span class="sxs-lookup"><span data-stu-id="a73f2-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="a73f2-109">[out]MethodBody トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="a73f2-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="a73f2-110">[out]MethodDeclaration トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="a73f2-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a73f2-111">[in]最大サイズ、`rMethodBody`と`rMethodDecl`配列。</span><span class="sxs-lookup"><span data-stu-id="a73f2-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a73f2-112">[in]実際のメソッドで返される数`rMethodBody`と`rMethodDecl`します。</span><span class="sxs-lookup"><span data-stu-id="a73f2-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a73f2-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="a73f2-113">Return Value</span></span>  
  
|<span data-ttu-id="a73f2-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a73f2-114">HRESULT</span></span>|<span data-ttu-id="a73f2-115">説明</span><span class="sxs-lookup"><span data-stu-id="a73f2-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a73f2-116">`EnumMethodImpls` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="a73f2-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a73f2-117">列挙するメソッドのトークンはありません。</span><span class="sxs-lookup"><span data-stu-id="a73f2-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="a73f2-118">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="a73f2-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a73f2-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="a73f2-119">Requirements</span></span>  
 <span data-ttu-id="a73f2-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a73f2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a73f2-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a73f2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a73f2-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a73f2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a73f2-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a73f2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73f2-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a73f2-124">See also</span></span>

- [<span data-ttu-id="a73f2-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a73f2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a73f2-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a73f2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
