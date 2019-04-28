---
title: IMetaDataTables::GetNumTables メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9ffd9ab9ddb95945744ecf210d0ae1d9d9812ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779813"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="abf3b-102">IMetaDataTables::GetNumTables メソッド</span><span class="sxs-lookup"><span data-stu-id="abf3b-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="abf3b-103">現在のスコープ内のテーブルの数を取得`IMetaDataTables`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf3b-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf3b-104">構文</span><span class="sxs-lookup"><span data-stu-id="abf3b-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abf3b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abf3b-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="abf3b-106">[out]現在のインスタンスのスコープ内のテーブルの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="abf3b-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf3b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="abf3b-107">Requirements</span></span>  
 <span data-ttu-id="abf3b-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf3b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf3b-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="abf3b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="abf3b-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="abf3b-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="abf3b-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf3b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf3b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="abf3b-112">See also</span></span>

- [<span data-ttu-id="abf3b-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abf3b-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="abf3b-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abf3b-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
