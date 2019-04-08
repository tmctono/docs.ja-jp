---
title: IMetaDataTables::GetBlobHeapSize メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076456"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="b3db2-102">IMetaDataTables::GetBlobHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="b3db2-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="b3db2-103">バイナリ ラージ オブジェクト (BLOB) ヒープのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3db2-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3db2-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3db2-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b3db2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3db2-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="b3db2-106">[out]BLOB ヒープのバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b3db2-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3db2-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3db2-107">Requirements</span></span>  
 <span data-ttu-id="b3db2-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3db2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3db2-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3db2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3db2-110">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b3db2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b3db2-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b3db2-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3db2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3db2-112">See also</span></span>

- [<span data-ttu-id="b3db2-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3db2-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b3db2-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3db2-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
