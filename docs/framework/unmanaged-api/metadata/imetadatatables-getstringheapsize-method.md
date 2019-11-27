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
ms.openlocfilehash: 43599a7e39ca4cc9d27dab43a948dc2f04e5010a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426677"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="8a28e-102">IMetaDataTables::GetStringHeapSize メソッド</span><span class="sxs-lookup"><span data-stu-id="8a28e-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="8a28e-103">文字列ヒープのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="8a28e-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a28e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a28e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a28e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a28e-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="8a28e-106">入出力文字列ヒープのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a28e-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a28e-107">要件</span><span class="sxs-lookup"><span data-stu-id="8a28e-107">Requirements</span></span>  
 <span data-ttu-id="8a28e-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a28e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a28e-109">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8a28e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a28e-110">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a28e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a28e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a28e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a28e-112">参照</span><span class="sxs-lookup"><span data-stu-id="8a28e-112">See also</span></span>

- [<span data-ttu-id="8a28e-113">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a28e-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8a28e-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a28e-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
