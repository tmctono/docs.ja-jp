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
ms.openlocfilehash: c32407c3fc0bc5a045b80ec48937699826d981af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177159"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="9f59a-102">IMetaDataTables::GetBlobHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9f59a-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="9f59a-103">バイナリ ラージ オブジェクト (BLOB) ヒープのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f59a-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f59a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f59a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="9f59a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f59a-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="9f59a-106">[アウト]BLOB ヒープのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9f59a-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f59a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f59a-107">Requirements</span></span>  
 <span data-ttu-id="9f59a-108">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f59a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f59a-109">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="9f59a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f59a-110">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f59a-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f59a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f59a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f59a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f59a-112">See also</span></span>

- [<span data-ttu-id="9f59a-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f59a-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="9f59a-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f59a-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
