---
title: IMetaDataTables::GetGuidHeapSize メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 812794bc76d475c516effdc950ca6a0b877494c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178361"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="01048-102">IMetaDataTables::GetGuidHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="01048-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="01048-103">GUID ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="01048-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01048-104">構文</span><span class="sxs-lookup"><span data-stu-id="01048-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01048-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01048-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="01048-106">[out]GUID ヒープのバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="01048-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01048-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="01048-107">Requirements</span></span>  
 <span data-ttu-id="01048-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01048-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01048-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="01048-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01048-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="01048-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01048-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01048-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01048-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="01048-112">See also</span></span>

- [<span data-ttu-id="01048-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01048-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="01048-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01048-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
