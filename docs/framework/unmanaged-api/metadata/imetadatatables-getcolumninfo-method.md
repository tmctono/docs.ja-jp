---
title: IMetaDataTables::GetColumnInfo メソッド
ms.date: 03/30/2017
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
ms.openlocfilehash: 6156499368fb743b69c03f38b40ad3c5bcabce6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992408"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="3bb88-102">IMetaDataTables::GetColumnInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="3bb88-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="3bb88-103">指定されたテーブルで指定された列に関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="3bb88-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb88-104">構文</span><span class="sxs-lookup"><span data-stu-id="3bb88-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bb88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bb88-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="3bb88-106">[in]目的のテーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="3bb88-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="3bb88-107">[in]必要な列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="3bb88-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="3bb88-108">[out]行内の列のオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bb88-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="3bb88-109">[out]列のバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bb88-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="3bb88-110">[out]列の値の型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bb88-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="3bb88-111">[out]列の名前へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3bb88-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb88-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3bb88-112">Requirements</span></span>  
 <span data-ttu-id="3bb88-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bb88-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb88-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3bb88-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bb88-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3bb88-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3bb88-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb88-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb88-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bb88-117">See also</span></span>

- [<span data-ttu-id="3bb88-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bb88-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3bb88-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bb88-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
