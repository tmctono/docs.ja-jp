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
ms.openlocfilehash: 715456317b880de89b6abdf1fa82acd040d17ced
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442041"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="af800-102">IMetaDataTables::GetBlobHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="af800-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="af800-103">バイナリラージオブジェクト (BLOB) ヒープのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="af800-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af800-104">構文</span><span class="sxs-lookup"><span data-stu-id="af800-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="af800-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af800-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="af800-106">入出力BLOB ヒープのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="af800-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af800-107">要件</span><span class="sxs-lookup"><span data-stu-id="af800-107">Requirements</span></span>  
 <span data-ttu-id="af800-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af800-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af800-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="af800-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af800-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="af800-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af800-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af800-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af800-112">参照</span><span class="sxs-lookup"><span data-stu-id="af800-112">See also</span></span>

- [<span data-ttu-id="af800-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af800-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="af800-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af800-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
