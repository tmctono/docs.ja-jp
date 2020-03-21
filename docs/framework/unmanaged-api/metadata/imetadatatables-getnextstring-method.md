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
ms.openlocfilehash: a1cd932051a9ed90a29ff5eeaa818a67104192bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175253"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="925d6-102">IMetaDataTables::GetNextString メソッド</span><span class="sxs-lookup"><span data-stu-id="925d6-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="925d6-103">現在のテーブル列の次の文字列のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="925d6-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="925d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="925d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="925d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="925d6-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="925d6-106">[in]文字列テーブル列のインデックス値。</span><span class="sxs-lookup"><span data-stu-id="925d6-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="925d6-107">[アウト]列内の次の文字列のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="925d6-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="925d6-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="925d6-108">Requirements</span></span>  
 <span data-ttu-id="925d6-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925d6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="925d6-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="925d6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="925d6-111">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="925d6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="925d6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="925d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925d6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="925d6-113">See also</span></span>

- [<span data-ttu-id="925d6-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="925d6-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="925d6-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="925d6-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
