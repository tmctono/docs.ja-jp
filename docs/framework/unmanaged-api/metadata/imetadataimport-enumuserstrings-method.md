---
title: IMetaDataImport::EnumUserStrings メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea144784f82c192f41f68394eb2ccdf443db54c2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782551"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="d9e02-102">IMetaDataImport::EnumUserStrings メソッド</span><span class="sxs-lookup"><span data-stu-id="d9e02-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="d9e02-103">現在のメタデータ スコープ内にあるハードコーディングされた文字列を表す String トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d9e02-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e02-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9e02-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9e02-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9e02-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d9e02-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9e02-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d9e02-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="d9e02-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="d9e02-108">[out]文字列トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="d9e02-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d9e02-109">[in] `rStrings` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d9e02-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="d9e02-110">[out]文字列のトークンで返される数`rStrings`します。</span><span class="sxs-lookup"><span data-stu-id="d9e02-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9e02-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d9e02-111">Return Value</span></span>  
  
|<span data-ttu-id="d9e02-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9e02-112">HRESULT</span></span>|<span data-ttu-id="d9e02-113">説明</span><span class="sxs-lookup"><span data-stu-id="d9e02-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d9e02-114">`EnumUserStrings` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d9e02-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d9e02-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="d9e02-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d9e02-116">その場合は、`pcStrings`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d9e02-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9e02-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9e02-117">Remarks</span></span>  
 <span data-ttu-id="d9e02-118">文字列トークンがによって作成された、 [imetadataemit::defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d9e02-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="d9e02-119">このメソッドは、コンパイラではなくメタデータ ブラウザーで使用する設計されています。</span><span class="sxs-lookup"><span data-stu-id="d9e02-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e02-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9e02-120">Requirements</span></span>  
 <span data-ttu-id="d9e02-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9e02-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e02-122">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9e02-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9e02-123">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d9e02-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9e02-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e02-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e02-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9e02-125">See also</span></span>

- [<span data-ttu-id="d9e02-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9e02-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d9e02-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9e02-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
