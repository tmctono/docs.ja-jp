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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225431"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="d237b-102">ICLRDataEnumMemoryRegionsCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d237b-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="d237b-103">コールバック メソッドを提供します[iclrdataenummemoryregions::enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)メモリの指定した領域の列挙の試行の結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="d237b-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d237b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d237b-104">Methods</span></span>  
  
|<span data-ttu-id="d237b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d237b-105">Method</span></span>|<span data-ttu-id="d237b-106">説明</span><span class="sxs-lookup"><span data-stu-id="d237b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d237b-107">EnumMemoryRegion メソッド</span><span class="sxs-lookup"><span data-stu-id="d237b-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="d237b-108">によって呼び出される`ICLRDataEnumMemoryRegions::EnumMemoryRegions`メモリの指定した領域の列挙の試行の結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="d237b-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d237b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d237b-109">Requirements</span></span>  
 <span data-ttu-id="d237b-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d237b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d237b-111">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d237b-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d237b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d237b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d237b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d237b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d237b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d237b-114">See also</span></span>

- [<span data-ttu-id="d237b-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d237b-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
