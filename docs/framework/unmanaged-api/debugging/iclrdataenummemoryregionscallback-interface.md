---
title: ICLRDataEnumMemoryRegionsCallback インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: cf46133095d1345ffbe0356d3ab486c11ae6dbd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122910"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="44e35-102">ICLRDataEnumMemoryRegionsCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44e35-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="44e35-103">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)のコールバックメソッドを提供し、指定されたメモリ領域を列挙しようとした結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="44e35-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44e35-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="44e35-104">Methods</span></span>  
  
|<span data-ttu-id="44e35-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="44e35-105">Method</span></span>|<span data-ttu-id="44e35-106">説明</span><span class="sxs-lookup"><span data-stu-id="44e35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44e35-107">EnumMemoryRegion メソッド</span><span class="sxs-lookup"><span data-stu-id="44e35-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="44e35-108">指定されたメモリ領域を列挙しようとした結果をデバッガーに報告するために、`ICLRDataEnumMemoryRegions::EnumMemoryRegions` によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44e35-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44e35-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="44e35-109">Requirements</span></span>  
 <span data-ttu-id="44e35-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44e35-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e35-111">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="44e35-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="44e35-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44e35-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44e35-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e35-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e35-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="44e35-114">See also</span></span>

- [<span data-ttu-id="44e35-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44e35-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
