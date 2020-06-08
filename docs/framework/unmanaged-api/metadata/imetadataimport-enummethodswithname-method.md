---
title: IMetaDataImport::EnumMethodsWithName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 66a09baea1df2e2de418bdce8821672802f1f51f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491733"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="7c054-102">IMetaDataImport::EnumMethodsWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="7c054-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="7c054-103">指定された名前を持ち、指定された TypeDef トークンによって参照される型で定義されているメソッドを列挙します。</span><span class="sxs-lookup"><span data-stu-id="7c054-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c054-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c054-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c054-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c054-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7c054-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7c054-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7c054-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c054-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="7c054-108">から列挙するメソッドを持つ型を表す TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="7c054-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="7c054-109">から列挙型のスコープを制限する名前。</span><span class="sxs-lookup"><span data-stu-id="7c054-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="7c054-110">入出力MethodDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="7c054-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7c054-111">[in] `rMethods` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="7c054-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7c054-112">入出力で返される MethodDef トークンの数 `rMethods` 。</span><span class="sxs-lookup"><span data-stu-id="7c054-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c054-113">解説</span><span class="sxs-lookup"><span data-stu-id="7c054-113">Remarks</span></span>  
 <span data-ttu-id="7c054-114">このメソッドは、フィールドとメソッドを列挙しますが、プロパティやイベントは列挙しません。</span><span class="sxs-lookup"><span data-stu-id="7c054-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="7c054-115">[IMetaDataImport:: enummethods](imetadataimport-enummethods-method.md)とは異なり、は、 `EnumMethodsWithName` 指定された名前を持たないすべてのメソッドトークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="7c054-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c054-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="7c054-116">Return Value</span></span>  
  
|<span data-ttu-id="7c054-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c054-117">HRESULT</span></span>|<span data-ttu-id="7c054-118">説明</span><span class="sxs-lookup"><span data-stu-id="7c054-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7c054-119">`EnumMethodsWithName`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7c054-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7c054-120">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="7c054-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="7c054-121">この場合、 `pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="7c054-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c054-122">要件</span><span class="sxs-lookup"><span data-stu-id="7c054-122">Requirements</span></span>  
 <span data-ttu-id="7c054-123">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c054-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c054-124">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="7c054-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c054-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7c054-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c054-126">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c054-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c054-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c054-127">See also</span></span>

- [<span data-ttu-id="7c054-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c054-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7c054-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c054-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
