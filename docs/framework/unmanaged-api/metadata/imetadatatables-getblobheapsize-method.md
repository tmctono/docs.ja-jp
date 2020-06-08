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
ms.openlocfilehash: 68e29e932e477f286db00b0c989a3346bd13c9bc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501223"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="035ae-102">IMetaDataTables::GetBlobHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="035ae-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="035ae-103">バイナリラージオブジェクト (BLOB) ヒープのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="035ae-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="035ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="035ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="035ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="035ae-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="035ae-106">入出力BLOB ヒープのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="035ae-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="035ae-107">要件</span><span class="sxs-lookup"><span data-stu-id="035ae-107">Requirements</span></span>  
 <span data-ttu-id="035ae-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="035ae-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="035ae-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="035ae-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="035ae-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="035ae-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="035ae-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="035ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="035ae-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="035ae-112">See also</span></span>

- [<span data-ttu-id="035ae-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="035ae-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="035ae-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="035ae-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
