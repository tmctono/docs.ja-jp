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
ms.openlocfilehash: 8fed98521c0609ebd8b5f65885d69c77814e9e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119341"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="b08fe-102">IMetaDataTables::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="b08fe-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="b08fe-103">参照の現在のスコープ内のテーブル列から、指定したインデックス位置にある文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="b08fe-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="b08fe-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b08fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b08fe-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="b08fe-106">[in][次へ] の値の検索を開始する位置のインデックス。</span><span class="sxs-lookup"><span data-stu-id="b08fe-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="b08fe-107">[out]返される文字列値へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b08fe-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b08fe-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="b08fe-108">Requirements</span></span>  
 <span data-ttu-id="b08fe-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b08fe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b08fe-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b08fe-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b08fe-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b08fe-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b08fe-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b08fe-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b08fe-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b08fe-113">See also</span></span>

- [<span data-ttu-id="b08fe-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b08fe-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b08fe-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b08fe-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
