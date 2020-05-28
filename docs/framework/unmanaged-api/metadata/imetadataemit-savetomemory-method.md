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
ms.openlocfilehash: ccf82531eb1f78bcfc6762d10d53ffee59f30ad8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003953"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="2c713-102">IMetaDataEmit::SaveToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="2c713-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="2c713-103">現在のスコープ内のすべてのメタデータを、指定したメモリ領域に保存します。</span><span class="sxs-lookup"><span data-stu-id="2c713-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c713-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c713-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c713-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c713-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="2c713-106">入出力メタデータの書き込みを開始するアドレス。</span><span class="sxs-lookup"><span data-stu-id="2c713-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="2c713-107">から割り当てられたメモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="2c713-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c713-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c713-108">Requirements</span></span>  
 <span data-ttu-id="2c713-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c713-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c713-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2c713-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c713-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c713-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c713-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c713-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c713-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c713-113">See also</span></span>

- [<span data-ttu-id="2c713-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c713-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2c713-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c713-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
