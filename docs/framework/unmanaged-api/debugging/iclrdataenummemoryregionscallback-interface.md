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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dad66c8a55982762ede754a4b3cd747b7a91b87d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698188"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="e3b01-102">ICLRDataEnumMemoryRegionsCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3b01-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="e3b01-103">コールバック メソッドを提供します[iclrdataenummemoryregions::enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)メモリの指定した領域の列挙の試行の結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="e3b01-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3b01-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e3b01-104">Methods</span></span>  
  
|<span data-ttu-id="e3b01-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e3b01-105">Method</span></span>|<span data-ttu-id="e3b01-106">説明</span><span class="sxs-lookup"><span data-stu-id="e3b01-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3b01-107">EnumMemoryRegion メソッド</span><span class="sxs-lookup"><span data-stu-id="e3b01-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="e3b01-108">によって呼び出される`ICLRDataEnumMemoryRegions::EnumMemoryRegions`メモリの指定した領域の列挙の試行の結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="e3b01-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3b01-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e3b01-109">Requirements</span></span>  
 <span data-ttu-id="e3b01-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b01-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b01-111">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e3b01-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e3b01-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3b01-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3b01-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b01-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b01-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3b01-114">See also</span></span>

- [<span data-ttu-id="e3b01-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e3b01-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
