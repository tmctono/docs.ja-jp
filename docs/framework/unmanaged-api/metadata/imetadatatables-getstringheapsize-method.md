---
title: IMetaDataTables::GetStringHeapSize メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a46f7b277987df7e15eb2d534d1bbacc3250f4e1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466012"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="6de70-102">IMetaDataTables::GetStringHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="6de70-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="6de70-103">文字列ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="6de70-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de70-104">構文</span><span class="sxs-lookup"><span data-stu-id="6de70-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de70-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6de70-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="6de70-106">[out]文字列ヒープのバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6de70-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de70-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6de70-107">Requirements</span></span>  
 <span data-ttu-id="6de70-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6de70-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de70-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6de70-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6de70-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6de70-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6de70-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de70-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de70-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6de70-112">See also</span></span>
- [<span data-ttu-id="6de70-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6de70-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6de70-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6de70-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
