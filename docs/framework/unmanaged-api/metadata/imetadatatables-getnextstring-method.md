---
title: IMetaDataTables::GetNextString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b057b0537bbeff7433b776e64456ccc810cee54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473488"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="3a38d-102">IMetaDataTables::GetNextString メソッド</span><span class="sxs-lookup"><span data-stu-id="3a38d-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="3a38d-103">現在のテーブルの列には、次の文字列のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a38d-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a38d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a38d-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a38d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a38d-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="3a38d-106">[in]文字列テーブルの列からインデックス値。</span><span class="sxs-lookup"><span data-stu-id="3a38d-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="3a38d-107">[out]次の列に文字列のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a38d-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a38d-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a38d-108">Requirements</span></span>  
 <span data-ttu-id="3a38d-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a38d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a38d-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a38d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a38d-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3a38d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a38d-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a38d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a38d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a38d-113">See also</span></span>
- [<span data-ttu-id="3a38d-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a38d-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3a38d-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a38d-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
