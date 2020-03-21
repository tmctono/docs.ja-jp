---
title: IMetaDataTables::GetColumn メソッド
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177135"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="c8554-102">IMetaDataTables::GetColumn メソッド</span><span class="sxs-lookup"><span data-stu-id="c8554-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="c8554-103">指定したテーブルの指定した列と行のセルに含まれる値へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8554-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8554-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8554-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8554-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8554-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="c8554-106">[in]テーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="c8554-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="c8554-107">[in]テーブル内の列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="c8554-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="c8554-108">[in]テーブル内の行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="c8554-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="c8554-109">[アウト]セル内の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c8554-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="c8554-110">解説</span><span class="sxs-lookup"><span data-stu-id="c8554-110">Remarks</span></span>

<span data-ttu-id="c8554-111">返される値の解釈は、列の`pVal`型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c8554-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="c8554-112">列の型は、[呼](imetadatatables-getcolumninfo-method.md)び出すことによって決定できます。</span><span class="sxs-lookup"><span data-stu-id="c8554-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="c8554-113">**GetColumn**メソッドは **、Rid**型または**CodedToken**型の列を 32 ビット`mdToken`の完全な値に自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="c8554-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="c8554-114">また、8 ビットまたは 16 ビットの値を 32 ビットの値に自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="c8554-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="c8554-115">*ヒープ*型の列の場合、返される*pVal*は対応するヒープへのインデックスになります。</span><span class="sxs-lookup"><span data-stu-id="c8554-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="c8554-116">列の型</span><span class="sxs-lookup"><span data-stu-id="c8554-116">Column type</span></span>              | <span data-ttu-id="c8554-117">pVal に含まれる</span><span class="sxs-lookup"><span data-stu-id="c8554-117">pVal contains</span></span> | <span data-ttu-id="c8554-118">解説</span><span class="sxs-lookup"><span data-stu-id="c8554-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="c8554-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="c8554-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="c8554-120">(0..63)</span><span class="sxs-lookup"><span data-stu-id="c8554-120">(0..63)</span></span>  | <span data-ttu-id="c8554-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="c8554-121">mdToken</span></span>     | <span data-ttu-id="c8554-122">*pVal*には完全なトークンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8554-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="c8554-123">この関数は、Rid を完全なトークンに自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="c8554-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="c8554-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="c8554-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="c8554-125">(64..95)</span><span class="sxs-lookup"><span data-stu-id="c8554-125">(64..95)</span></span> | <span data-ttu-id="c8554-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="c8554-126">mdToken</span></span> | <span data-ttu-id="c8554-127">戻り値が返されると *、pVal*には完全なトークンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8554-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="c8554-128">この関数は、CodedToken を自動的に完全なトークンに解凍します。</span><span class="sxs-lookup"><span data-stu-id="c8554-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="c8554-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="c8554-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="c8554-130">Int16</span><span class="sxs-lookup"><span data-stu-id="c8554-130">Int16</span></span>         | <span data-ttu-id="c8554-131">自動的に 32 ビットに拡張されます。</span><span class="sxs-lookup"><span data-stu-id="c8554-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="c8554-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="c8554-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="c8554-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="c8554-133">UInt16</span></span>        | <span data-ttu-id="c8554-134">自動的に 32 ビットに拡張されます。</span><span class="sxs-lookup"><span data-stu-id="c8554-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="c8554-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="c8554-135">`iLONG` (98)</span></span>             | <span data-ttu-id="c8554-136">Int32</span><span class="sxs-lookup"><span data-stu-id="c8554-136">Int32</span></span>         |                                        |
| <span data-ttu-id="c8554-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="c8554-137">`iULONG` (99)</span></span>            | <span data-ttu-id="c8554-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="c8554-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="c8554-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="c8554-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="c8554-140">Byte</span><span class="sxs-lookup"><span data-stu-id="c8554-140">Byte</span></span>          | <span data-ttu-id="c8554-141">自動的に 32 ビットに拡張されます。</span><span class="sxs-lookup"><span data-stu-id="c8554-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="c8554-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="c8554-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="c8554-143">文字列ヒープインデックス</span><span class="sxs-lookup"><span data-stu-id="c8554-143">String heap index</span></span> | <span data-ttu-id="c8554-144">*pVal*は、文字列ヒープへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="c8554-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="c8554-145">実際の列の文字列値を取得するには[、IMetadataTables::GetString](imetadatatables-getstring-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8554-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="c8554-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="c8554-146">`iGUID` (102)</span></span>            | <span data-ttu-id="c8554-147">GUID ヒープ インデックス</span><span class="sxs-lookup"><span data-stu-id="c8554-147">Guid heap index</span></span> | <span data-ttu-id="c8554-148">*pVal*は、GUID ヒープへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="c8554-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="c8554-149">実際の列 Guid 値を取得するには[、IMetadataTables::GetGuid](imetadatatables-getguid-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8554-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="c8554-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="c8554-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="c8554-151">BLOB ヒープ インデックス</span><span class="sxs-lookup"><span data-stu-id="c8554-151">Blob heap index</span></span> | <span data-ttu-id="c8554-152">*pVal*は、BLOB ヒープへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="c8554-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="c8554-153">実際の列の BLOB 値を取得するには[、IMetadataTables::GetBlob](imetadatatables-getblob-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8554-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="c8554-154">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8554-154">Requirements</span></span>  
 <span data-ttu-id="c8554-155">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8554-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8554-156">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="c8554-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8554-157">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8554-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8554-158">**.NET フレームワークのバージョン**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8554-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8554-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8554-159">See also</span></span>

- [<span data-ttu-id="c8554-160">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8554-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c8554-161">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8554-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
