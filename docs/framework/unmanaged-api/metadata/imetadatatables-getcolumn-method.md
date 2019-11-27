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
ms.openlocfilehash: 376b9ff09ad38ca43d57fcf064458e0331da8aad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441999"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="6efd1-102">IMetaDataTables::GetColumn メソッド</span><span class="sxs-lookup"><span data-stu-id="6efd1-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="6efd1-103">指定したテーブル内の指定した列および行のセルに格納されている値へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6efd1-104">構文</span><span class="sxs-lookup"><span data-stu-id="6efd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6efd1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6efd1-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="6efd1-106">からテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="6efd1-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="6efd1-107">からテーブル内の列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="6efd1-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="6efd1-108">からテーブル内の行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="6efd1-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="6efd1-109">入出力セル内の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6efd1-109">[out] A pointer to the value in the cell.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="6efd1-110">コメント</span><span class="sxs-lookup"><span data-stu-id="6efd1-110">Remarks</span></span>

<span data-ttu-id="6efd1-111">`pVal` によって返される値の interpretion は、列の型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6efd1-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="6efd1-112">列の型は、 [GetColumnInfo](imetadatatables-getcolumninfo-method.md)を呼び出すことによって決定できます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="6efd1-113">**Getcolumn**メソッドは、 **Rid**または**codedtoken**型の列を、完全な32ビット `mdToken` 値に自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="6efd1-114">また、8ビットまたは16ビットの値を完全な32ビット値に自動的に変換します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span> 
- <span data-ttu-id="6efd1-115">*ヒープ*型の列の場合、返される*pVal*は、対応するヒープのインデックスになります。</span><span class="sxs-lookup"><span data-stu-id="6efd1-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="6efd1-116">列の型</span><span class="sxs-lookup"><span data-stu-id="6efd1-116">Column type</span></span>              | <span data-ttu-id="6efd1-117">pVal を含む</span><span class="sxs-lookup"><span data-stu-id="6efd1-117">pVal contains</span></span> | <span data-ttu-id="6efd1-118">コメント</span><span class="sxs-lookup"><span data-stu-id="6efd1-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="6efd1-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="6efd1-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="6efd1-120">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="6efd1-120">(0..63)</span></span>  | <span data-ttu-id="6efd1-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="6efd1-121">mdToken</span></span>     | <span data-ttu-id="6efd1-122">*pVal*には完全なトークンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="6efd1-123">関数は、自動的に Rid を完全なトークンに変換します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="6efd1-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="6efd1-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="6efd1-125">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="6efd1-125">(64..95)</span></span> | <span data-ttu-id="6efd1-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="6efd1-126">mdToken</span></span> | <span data-ttu-id="6efd1-127">返されると、 *pVal*には完全なトークンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="6efd1-128">関数は、CodedToken を完全なトークンに自動的に圧縮解除します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="6efd1-129">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="6efd1-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="6efd1-130">Int16</span><span class="sxs-lookup"><span data-stu-id="6efd1-130">Int16</span></span>         | <span data-ttu-id="6efd1-131">32ビットに自動的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="6efd1-132">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="6efd1-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="6efd1-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="6efd1-133">UInt16</span></span>        | <span data-ttu-id="6efd1-134">32ビットに自動的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="6efd1-135">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="6efd1-135">`iLONG` (98)</span></span>             | <span data-ttu-id="6efd1-136">Int32</span><span class="sxs-lookup"><span data-stu-id="6efd1-136">Int32</span></span>         |                                        | 
| <span data-ttu-id="6efd1-137">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="6efd1-137">`iULONG` (99)</span></span>            | <span data-ttu-id="6efd1-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="6efd1-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="6efd1-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="6efd1-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="6efd1-140">バイト</span><span class="sxs-lookup"><span data-stu-id="6efd1-140">Byte</span></span>          | <span data-ttu-id="6efd1-141">32ビットに自動的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="6efd1-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="6efd1-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="6efd1-143">文字列ヒープインデックス</span><span class="sxs-lookup"><span data-stu-id="6efd1-143">String heap index</span></span> | <span data-ttu-id="6efd1-144">*pVal*は、文字列ヒープのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="6efd1-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="6efd1-145">実際の列文字列値を取得するには、 [Imetadatatables::](imetadatatables-getstring-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="6efd1-146">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="6efd1-146">`iGUID` (102)</span></span>            | <span data-ttu-id="6efd1-147">Guid ヒープインデックス</span><span class="sxs-lookup"><span data-stu-id="6efd1-147">Guid heap index</span></span> | <span data-ttu-id="6efd1-148">*pVal*は、Guid ヒープのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="6efd1-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="6efd1-149">実際の列の Guid 値を取得するには、 [Imetadatatables 指定できる:: GetGuid](imetadatatables-getguid-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="6efd1-150">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="6efd1-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="6efd1-151">Blob ヒープインデックス</span><span class="sxs-lookup"><span data-stu-id="6efd1-151">Blob heap index</span></span> | <span data-ttu-id="6efd1-152">*pVal*は、Blob ヒープのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="6efd1-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="6efd1-153">実際の列の Blob 値を取得するには、 [Imetadatatables 指定できる:: GetBlob](imetadatatables-getblob-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="6efd1-154">要件</span><span class="sxs-lookup"><span data-stu-id="6efd1-154">Requirements</span></span>  
 <span data-ttu-id="6efd1-155">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efd1-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6efd1-156">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6efd1-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6efd1-157">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6efd1-158">**.NET Framework のバージョン**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6efd1-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efd1-159">参照</span><span class="sxs-lookup"><span data-stu-id="6efd1-159">See also</span></span>

- [<span data-ttu-id="6efd1-160">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6efd1-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6efd1-161">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6efd1-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
