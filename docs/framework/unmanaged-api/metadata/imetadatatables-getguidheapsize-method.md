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
ms.openlocfilehash: 0ddbd1c034708326d75c59f8ed4764156f617b81
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781490"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="c0508-102">IMetaDataTables::GetGuidHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="c0508-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="c0508-103">GUID ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="c0508-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0508-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0508-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0508-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0508-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="c0508-106">[out]GUID ヒープのバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0508-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0508-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0508-107">Requirements</span></span>  
 <span data-ttu-id="c0508-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0508-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0508-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0508-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0508-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="c0508-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0508-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0508-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0508-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0508-112">See also</span></span>

- [<span data-ttu-id="c0508-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0508-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c0508-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0508-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
