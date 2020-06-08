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
ms.openlocfilehash: 71a75defa72e4fe3594b4d0ceff45273b3a35395
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490355"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="b3ff9-102">IMetaDataTables::GetGuidHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="b3ff9-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="b3ff9-103">GUID ヒープのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ff9-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ff9-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3ff9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3ff9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3ff9-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="b3ff9-106">入出力GUID ヒープのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b3ff9-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3ff9-107">要件</span><span class="sxs-lookup"><span data-stu-id="b3ff9-107">Requirements</span></span>  
 <span data-ttu-id="b3ff9-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ff9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ff9-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="b3ff9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3ff9-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3ff9-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3ff9-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ff9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ff9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3ff9-112">See also</span></span>

- [<span data-ttu-id="b3ff9-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3ff9-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b3ff9-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3ff9-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
