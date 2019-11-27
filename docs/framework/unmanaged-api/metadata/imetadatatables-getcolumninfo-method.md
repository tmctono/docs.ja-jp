---
title: IMetaDataTables::GetColumnInfo メソッド
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: 854d3ad28cc00c03e903b9e1d2ce3863e3ceef17
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436097"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="3bfbd-102">IMetaDataTables::GetColumnInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="3bfbd-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="3bfbd-103">指定されたテーブル内の指定された列に関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bfbd-104">構文</span><span class="sxs-lookup"><span data-stu-id="3bfbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bfbd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bfbd-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="3bfbd-106">から目的のテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="3bfbd-107">から目的の列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="3bfbd-108">入出力行内の列のオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="3bfbd-109">入出力列のサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="3bfbd-110">入出力列内の値の型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="3bfbd-111">入出力列名へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-111">[out] A pointer to a pointer to the column name.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="3bfbd-112">コメント</span><span class="sxs-lookup"><span data-stu-id="3bfbd-112">Remarks</span></span>

<span data-ttu-id="3bfbd-113">返される列の型は、値の範囲内にあります。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="3bfbd-114">pType</span><span class="sxs-lookup"><span data-stu-id="3bfbd-114">pType</span></span>                    | <span data-ttu-id="3bfbd-115">説明</span><span class="sxs-lookup"><span data-stu-id="3bfbd-115">Description</span></span>   | <span data-ttu-id="3bfbd-116">ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="3bfbd-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="3bfbd-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="3bfbd-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="3bfbd-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-118">(0..63)</span></span>   | <span data-ttu-id="3bfbd-119">Rid</span><span class="sxs-lookup"><span data-stu-id="3bfbd-119">Rid</span></span>           | <span data-ttu-id="3bfbd-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-120">**IsRidType**</span></span><br><span data-ttu-id="3bfbd-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="3bfbd-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="3bfbd-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="3bfbd-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-123">(64..95)</span></span> | <span data-ttu-id="3bfbd-124">コード化されたトークン</span><span class="sxs-lookup"><span data-stu-id="3bfbd-124">Coded token</span></span> | <span data-ttu-id="3bfbd-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="3bfbd-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="3bfbd-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="3bfbd-128">Int16</span><span class="sxs-lookup"><span data-stu-id="3bfbd-128">Int16</span></span>         | <span data-ttu-id="3bfbd-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="3bfbd-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="3bfbd-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="3bfbd-131">UInt16</span></span>        | <span data-ttu-id="3bfbd-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="3bfbd-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-133">`iLONG` (98)</span></span>             | <span data-ttu-id="3bfbd-134">Int32</span><span class="sxs-lookup"><span data-stu-id="3bfbd-134">Int32</span></span>         | <span data-ttu-id="3bfbd-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="3bfbd-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-136">`iULONG` (99)</span></span>            | <span data-ttu-id="3bfbd-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="3bfbd-137">UInt32</span></span>        | <span data-ttu-id="3bfbd-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="3bfbd-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="3bfbd-140">バイト</span><span class="sxs-lookup"><span data-stu-id="3bfbd-140">Byte</span></span>          | <span data-ttu-id="3bfbd-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="3bfbd-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="3bfbd-143">String</span><span class="sxs-lookup"><span data-stu-id="3bfbd-143">String</span></span>        | <span data-ttu-id="3bfbd-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="3bfbd-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-145">`iGUID` (102)</span></span>            | <span data-ttu-id="3bfbd-146">Guid</span><span class="sxs-lookup"><span data-stu-id="3bfbd-146">Guid</span></span>          | <span data-ttu-id="3bfbd-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="3bfbd-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="3bfbd-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="3bfbd-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="3bfbd-149">Blob</span></span>          | <span data-ttu-id="3bfbd-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="3bfbd-151">*ヒープ*に格納されている値 (つまり `IsHeapType == true`) は、次の方法で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="3bfbd-152">`iSTRING`: **Imetadatatables**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="3bfbd-153">`iGUID`: **Imetadatatables 実行できます。 GetGUID**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="3bfbd-154">`iBLOB`: **Imetadatatables 実行できます。 GetBlob**</span><span class="sxs-lookup"><span data-stu-id="3bfbd-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bfbd-155">上の表で定義されている定数を使用するには、 *cor*ヘッダーファイルによって提供されるディレクティブ `#define _DEFINE_META_DATA_META_CONSTANTS` を含めます。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bfbd-156">要件</span><span class="sxs-lookup"><span data-stu-id="3bfbd-156">Requirements</span></span>  
 <span data-ttu-id="3bfbd-157">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfbd-158">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3bfbd-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bfbd-159">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3bfbd-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3bfbd-160">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bfbd-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfbd-161">参照</span><span class="sxs-lookup"><span data-stu-id="3bfbd-161">See also</span></span>

- [<span data-ttu-id="3bfbd-162">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bfbd-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3bfbd-163">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bfbd-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
