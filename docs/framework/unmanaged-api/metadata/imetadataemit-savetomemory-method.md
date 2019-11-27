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
ms.openlocfilehash: be4fb0b4b49408a97b318e0f54f5a753f3f24ef1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435797"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="6b2b5-102">IMetaDataEmit::SaveToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="6b2b5-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="6b2b5-103">現在のスコープ内のすべてのメタデータを、指定したメモリ領域に保存します。</span><span class="sxs-lookup"><span data-stu-id="6b2b5-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b2b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b2b5-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b2b5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b2b5-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="6b2b5-106">入出力メタデータの書き込みを開始するアドレス。</span><span class="sxs-lookup"><span data-stu-id="6b2b5-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="6b2b5-107">から割り当てられたメモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6b2b5-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b2b5-108">要件</span><span class="sxs-lookup"><span data-stu-id="6b2b5-108">Requirements</span></span>  
 <span data-ttu-id="6b2b5-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2b5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b2b5-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6b2b5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b2b5-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2b5-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b2b5-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b2b5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2b5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b2b5-113">See also</span></span>

- [<span data-ttu-id="6b2b5-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b2b5-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6b2b5-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b2b5-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
