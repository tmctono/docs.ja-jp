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
ms.openlocfilehash: b8fabea78f85448e39fc6d31f0a7969458343877
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492012"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="fda8a-102">IMetaDataImport::EnumMethodImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="fda8a-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="fda8a-103">指定した型のメソッドを表す MethodBody トークンと MethodDeclaration トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="fda8a-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda8a-104">構文</span><span class="sxs-lookup"><span data-stu-id="fda8a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fda8a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fda8a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fda8a-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fda8a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fda8a-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda8a-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="fda8a-108">から列挙するメソッド実装を持つ型の TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="fda8a-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="fda8a-109">入出力MethodBody トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="fda8a-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="fda8a-110">入出力MethodDeclaration トークンを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="fda8a-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fda8a-111">から`rMethodBody`配列と配列の最大サイズ `rMethodDecl` 。</span><span class="sxs-lookup"><span data-stu-id="fda8a-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fda8a-112">からとで返されるメソッドの実際の数 `rMethodBody` `rMethodDecl` 。</span><span class="sxs-lookup"><span data-stu-id="fda8a-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fda8a-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="fda8a-113">Return Value</span></span>  
  
|<span data-ttu-id="fda8a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fda8a-114">HRESULT</span></span>|<span data-ttu-id="fda8a-115">説明</span><span class="sxs-lookup"><span data-stu-id="fda8a-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fda8a-116">`EnumMethodImpls`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="fda8a-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fda8a-117">列挙するメソッドトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="fda8a-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="fda8a-118">この場合、 `pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="fda8a-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fda8a-119">要件</span><span class="sxs-lookup"><span data-stu-id="fda8a-119">Requirements</span></span>  
 <span data-ttu-id="fda8a-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fda8a-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fda8a-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="fda8a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fda8a-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="fda8a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fda8a-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fda8a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda8a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="fda8a-124">See also</span></span>

- [<span data-ttu-id="fda8a-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fda8a-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fda8a-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fda8a-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
