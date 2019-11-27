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
ms.openlocfilehash: 1c9f15881d3515f24a63f29e9337a7a356937f2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449946"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="42b7f-102">IMetaDataImport::EnumUserStrings メソッド</span><span class="sxs-lookup"><span data-stu-id="42b7f-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="42b7f-103">現在のメタデータ スコープ内にあるハードコーディングされた文字列を表す String トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="42b7f-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b7f-104">構文</span><span class="sxs-lookup"><span data-stu-id="42b7f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42b7f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42b7f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="42b7f-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="42b7f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="42b7f-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42b7f-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="42b7f-108">入出力文字列トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="42b7f-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="42b7f-109">[in] `rStrings` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="42b7f-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="42b7f-110">入出力`rStrings`で返された文字列トークンの数。</span><span class="sxs-lookup"><span data-stu-id="42b7f-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42b7f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="42b7f-111">Return Value</span></span>  
  
|<span data-ttu-id="42b7f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42b7f-112">HRESULT</span></span>|<span data-ttu-id="42b7f-113">説明</span><span class="sxs-lookup"><span data-stu-id="42b7f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="42b7f-114">`EnumUserStrings` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="42b7f-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="42b7f-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="42b7f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="42b7f-116">この場合、`pcStrings` は0になります。</span><span class="sxs-lookup"><span data-stu-id="42b7f-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42b7f-117">コメント</span><span class="sxs-lookup"><span data-stu-id="42b7f-117">Remarks</span></span>  
 <span data-ttu-id="42b7f-118">文字列トークンは、 [IMetaDataEmit::D efineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)メソッドによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="42b7f-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="42b7f-119">このメソッドは、コンパイラではなく、メタデータブラウザーによって使用されるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="42b7f-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42b7f-120">要件</span><span class="sxs-lookup"><span data-stu-id="42b7f-120">Requirements</span></span>  
 <span data-ttu-id="42b7f-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42b7f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42b7f-122">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="42b7f-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42b7f-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="42b7f-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42b7f-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42b7f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b7f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="42b7f-125">See also</span></span>

- [<span data-ttu-id="42b7f-126">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42b7f-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="42b7f-127">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42b7f-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
