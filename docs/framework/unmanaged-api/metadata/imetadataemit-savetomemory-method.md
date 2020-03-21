---
title: IMetaDataEmit::SaveToMemory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: d8843b2b5f69696dc206e9b530e3062ff225e89e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177582"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="8aafc-102">IMetaDataEmit::SaveToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="8aafc-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="8aafc-103">現在のスコープ内のすべてのメタデータを、指定されたメモリ領域に保存します。</span><span class="sxs-lookup"><span data-stu-id="8aafc-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aafc-104">構文</span><span class="sxs-lookup"><span data-stu-id="8aafc-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aafc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8aafc-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="8aafc-106">[アウト]メタデータの書き込みを開始するアドレス。</span><span class="sxs-lookup"><span data-stu-id="8aafc-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="8aafc-107">[in]割り当てられたメモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="8aafc-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aafc-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="8aafc-108">Requirements</span></span>  
 <span data-ttu-id="8aafc-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aafc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aafc-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="8aafc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8aafc-111">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="8aafc-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8aafc-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aafc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aafc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aafc-113">See also</span></span>

- [<span data-ttu-id="8aafc-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8aafc-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8aafc-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8aafc-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
