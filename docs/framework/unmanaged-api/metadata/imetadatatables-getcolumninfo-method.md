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
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177118"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="1a291-102">IMetaDataTables::GetColumnInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1a291-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="1a291-103">指定したテーブルの指定した列に関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a291-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a291-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a291-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1a291-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a291-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="1a291-106">[in]目的のテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="1a291-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="1a291-107">[in]目的の列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="1a291-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="1a291-108">[アウト]行の列のオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a291-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="1a291-109">[アウト]列のサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a291-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="1a291-110">[アウト]列の値の型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a291-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="1a291-111">[アウト]列名へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a291-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="1a291-112">解説</span><span class="sxs-lookup"><span data-stu-id="1a291-112">Remarks</span></span>

<span data-ttu-id="1a291-113">返される列の型は、値の範囲内にあります。</span><span class="sxs-lookup"><span data-stu-id="1a291-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="1a291-114">pタイプ</span><span class="sxs-lookup"><span data-stu-id="1a291-114">pType</span></span>                    | <span data-ttu-id="1a291-115">説明</span><span class="sxs-lookup"><span data-stu-id="1a291-115">Description</span></span>   | <span data-ttu-id="1a291-116">ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="1a291-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="1a291-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="1a291-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="1a291-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="1a291-118">(0..63)</span></span>   | <span data-ttu-id="1a291-119">解消</span><span class="sxs-lookup"><span data-stu-id="1a291-119">Rid</span></span>           | <span data-ttu-id="1a291-120">**イスリッドタイプ**</span><span class="sxs-lookup"><span data-stu-id="1a291-120">**IsRidType**</span></span><br><span data-ttu-id="1a291-121">**イスリドールトークン**</span><span class="sxs-lookup"><span data-stu-id="1a291-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="1a291-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="1a291-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="1a291-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="1a291-123">(64..95)</span></span> | <span data-ttu-id="1a291-124">コード化されたトークン</span><span class="sxs-lookup"><span data-stu-id="1a291-124">Coded token</span></span> | <span data-ttu-id="1a291-125">**タイプを指定します。**</span><span class="sxs-lookup"><span data-stu-id="1a291-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="1a291-126">**イスリドールトークン**</span><span class="sxs-lookup"><span data-stu-id="1a291-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="1a291-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="1a291-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="1a291-128">Int16</span><span class="sxs-lookup"><span data-stu-id="1a291-128">Int16</span></span>         | <span data-ttu-id="1a291-129">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="1a291-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="1a291-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="1a291-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="1a291-131">UInt16</span></span>        | <span data-ttu-id="1a291-132">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="1a291-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="1a291-133">`iLONG` (98)</span></span>             | <span data-ttu-id="1a291-134">Int32</span><span class="sxs-lookup"><span data-stu-id="1a291-134">Int32</span></span>         | <span data-ttu-id="1a291-135">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="1a291-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="1a291-136">`iULONG` (99)</span></span>            | <span data-ttu-id="1a291-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="1a291-137">UInt32</span></span>        | <span data-ttu-id="1a291-138">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="1a291-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="1a291-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="1a291-140">Byte</span><span class="sxs-lookup"><span data-stu-id="1a291-140">Byte</span></span>          | <span data-ttu-id="1a291-141">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="1a291-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="1a291-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="1a291-143">String</span><span class="sxs-lookup"><span data-stu-id="1a291-143">String</span></span>        | <span data-ttu-id="1a291-144">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="1a291-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="1a291-145">`iGUID` (102)</span></span>            | <span data-ttu-id="1a291-146">Guid</span><span class="sxs-lookup"><span data-stu-id="1a291-146">Guid</span></span>          | <span data-ttu-id="1a291-147">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="1a291-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="1a291-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="1a291-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="1a291-149">Blob</span></span>          | <span data-ttu-id="1a291-150">**型指定**</span><span class="sxs-lookup"><span data-stu-id="1a291-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="1a291-151">*ヒープ*に格納されている値 ( つまり、 `IsHeapType == true`) は、次の方法で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1a291-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="1a291-152">`iSTRING`:**取得文字列**</span><span class="sxs-lookup"><span data-stu-id="1a291-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="1a291-153">`iGUID`を取得**します。**</span><span class="sxs-lookup"><span data-stu-id="1a291-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="1a291-154">`iBLOB`を取得**します。**</span><span class="sxs-lookup"><span data-stu-id="1a291-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a291-155">上記の表で定義されている定数を使用するには`#define _DEFINE_META_DATA_META_CONSTANTS`*、cor.h*ヘッダー ファイルによって提供されるディレクティブをインクルードします。</span><span class="sxs-lookup"><span data-stu-id="1a291-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a291-156">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a291-156">Requirements</span></span>  
 <span data-ttu-id="1a291-157">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a291-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a291-158">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="1a291-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a291-159">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a291-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a291-160">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a291-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a291-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a291-161">See also</span></span>

- [<span data-ttu-id="1a291-162">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a291-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="1a291-163">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a291-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
