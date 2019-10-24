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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd67d9faafedf4fb92c69618d4464ebb2ce47dcc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774260"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="c603f-102">IMetaDataTables::GetColumnInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="c603f-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="c603f-103">指定されたテーブル内の指定された列に関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c603f-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c603f-104">構文</span><span class="sxs-lookup"><span data-stu-id="c603f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c603f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c603f-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="c603f-106">から目的のテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="c603f-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="c603f-107">から目的の列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="c603f-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="c603f-108">入出力行内の列のオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c603f-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="c603f-109">入出力列のサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c603f-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="c603f-110">入出力列内の値の型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c603f-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="c603f-111">入出力列名へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c603f-111">[out] A pointer to a pointer to the column name.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="c603f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c603f-112">Remarks</span></span>

<span data-ttu-id="c603f-113">返される列の型は、値の範囲内にあります。</span><span class="sxs-lookup"><span data-stu-id="c603f-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="c603f-114">pType</span><span class="sxs-lookup"><span data-stu-id="c603f-114">pType</span></span>                    | <span data-ttu-id="c603f-115">説明</span><span class="sxs-lookup"><span data-stu-id="c603f-115">Description</span></span>   | <span data-ttu-id="c603f-116">ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="c603f-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="c603f-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="c603f-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="c603f-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="c603f-118">(0..63)</span></span>   | <span data-ttu-id="c603f-119">Rid</span><span class="sxs-lookup"><span data-stu-id="c603f-119">Rid</span></span>           | <span data-ttu-id="c603f-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="c603f-120">**IsRidType**</span></span><br><span data-ttu-id="c603f-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="c603f-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="c603f-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="c603f-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="c603f-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="c603f-123">(64..95)</span></span> | <span data-ttu-id="c603f-124">コード化されたトークン</span><span class="sxs-lookup"><span data-stu-id="c603f-124">Coded token</span></span> | <span data-ttu-id="c603f-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="c603f-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="c603f-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="c603f-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="c603f-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="c603f-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="c603f-128">Int16</span><span class="sxs-lookup"><span data-stu-id="c603f-128">Int16</span></span>         | <span data-ttu-id="c603f-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c603f-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c603f-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="c603f-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="c603f-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="c603f-131">UInt16</span></span>        | <span data-ttu-id="c603f-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c603f-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c603f-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="c603f-133">`iLONG` (98)</span></span>             | <span data-ttu-id="c603f-134">Int32</span><span class="sxs-lookup"><span data-stu-id="c603f-134">Int32</span></span>         | <span data-ttu-id="c603f-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c603f-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c603f-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="c603f-136">`iULONG` (99)</span></span>            | <span data-ttu-id="c603f-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="c603f-137">UInt32</span></span>        | <span data-ttu-id="c603f-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c603f-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c603f-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="c603f-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="c603f-140">Byte</span><span class="sxs-lookup"><span data-stu-id="c603f-140">Byte</span></span>          | <span data-ttu-id="c603f-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c603f-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c603f-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="c603f-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="c603f-143">文字列型</span><span class="sxs-lookup"><span data-stu-id="c603f-143">String</span></span>        | <span data-ttu-id="c603f-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="c603f-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="c603f-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="c603f-145">`iGUID` (102)</span></span>            | <span data-ttu-id="c603f-146">GUID</span><span class="sxs-lookup"><span data-stu-id="c603f-146">Guid</span></span>          | <span data-ttu-id="c603f-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="c603f-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="c603f-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="c603f-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="c603f-149">Blob</span><span class="sxs-lookup"><span data-stu-id="c603f-149">Blob</span></span>          | <span data-ttu-id="c603f-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="c603f-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="c603f-151">*ヒープ*に格納されている値 (つまり `IsHeapType == true`) は、次の方法で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c603f-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="c603f-152">`iSTRING`: **Imetadatatables**</span><span class="sxs-lookup"><span data-stu-id="c603f-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="c603f-153">`iGUID`: **Imetadatatables 実行できます。 GetGUID**</span><span class="sxs-lookup"><span data-stu-id="c603f-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="c603f-154">`iBLOB`: **Imetadatatables 実行できます。 GetBlob**</span><span class="sxs-lookup"><span data-stu-id="c603f-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c603f-155">上の表で定義されている定数を使用するには、 *cor*ヘッダーファイルによって提供されるディレクティブ `#define _DEFINE_META_DATA_META_CONSTANTS` を含めます。</span><span class="sxs-lookup"><span data-stu-id="c603f-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="c603f-156">［要件］</span><span class="sxs-lookup"><span data-stu-id="c603f-156">Requirements</span></span>  
 <span data-ttu-id="c603f-157">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c603f-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c603f-158">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="c603f-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c603f-159">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="c603f-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c603f-160">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c603f-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c603f-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="c603f-161">See also</span></span>

- [<span data-ttu-id="c603f-162">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c603f-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c603f-163">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c603f-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
