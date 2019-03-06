---
title: IMetaDataTables::GetUserStringHeapSize メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1215da0816c1fc7cdfaee0da167118909f8e5eb3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466103"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="261fd-102">IMetaDataTables::GetUserStringHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="261fd-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="261fd-103">ユーザー文字列ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="261fd-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="261fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="261fd-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="261fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="261fd-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="261fd-106">[out]ユーザー文字列ヒープのバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="261fd-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="261fd-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="261fd-107">Requirements</span></span>  
 <span data-ttu-id="261fd-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="261fd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="261fd-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="261fd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="261fd-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="261fd-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="261fd-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="261fd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="261fd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="261fd-112">See also</span></span>
- [<span data-ttu-id="261fd-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="261fd-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="261fd-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="261fd-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
