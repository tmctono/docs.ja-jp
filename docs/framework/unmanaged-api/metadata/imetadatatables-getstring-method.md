---
title: IMetaDataTables::GetString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f817fa3f24bebf3303c656bd02c4d93d1d1431b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781398"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="19501-102">IMetaDataTables::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="19501-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="19501-103">参照の現在のスコープ内のテーブル列から、指定したインデックス位置にある文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="19501-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19501-104">構文</span><span class="sxs-lookup"><span data-stu-id="19501-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19501-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19501-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="19501-106">[in][次へ] の値の検索を開始する位置のインデックス。</span><span class="sxs-lookup"><span data-stu-id="19501-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="19501-107">[out]返される文字列値へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="19501-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19501-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="19501-108">Requirements</span></span>  
 <span data-ttu-id="19501-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19501-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19501-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="19501-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19501-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="19501-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19501-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19501-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19501-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="19501-113">See also</span></span>

- [<span data-ttu-id="19501-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19501-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="19501-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19501-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
