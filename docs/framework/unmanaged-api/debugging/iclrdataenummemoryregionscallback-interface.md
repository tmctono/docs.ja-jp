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
ms.openlocfilehash: 4e3891996af5945ed95c8c37dddfee5c446db248
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789115"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="47742-102">ICLRDataEnumMemoryRegionsCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="47742-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="47742-103">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md)のコールバックメソッドを提供し、指定されたメモリ領域を列挙しようとした結果をデバッガーに報告します。</span><span class="sxs-lookup"><span data-stu-id="47742-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47742-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="47742-104">Methods</span></span>  
  
|<span data-ttu-id="47742-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="47742-105">Method</span></span>|<span data-ttu-id="47742-106">説明</span><span class="sxs-lookup"><span data-stu-id="47742-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47742-107">EnumMemoryRegion メソッド</span><span class="sxs-lookup"><span data-stu-id="47742-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="47742-108">指定されたメモリ領域を列挙しようとした結果をデバッガーに報告するために、`ICLRDataEnumMemoryRegions::EnumMemoryRegions` によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="47742-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47742-109">要件</span><span class="sxs-lookup"><span data-stu-id="47742-109">Requirements</span></span>  
 <span data-ttu-id="47742-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47742-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47742-111">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="47742-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="47742-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47742-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47742-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47742-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47742-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="47742-114">See also</span></span>

- [<span data-ttu-id="47742-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="47742-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
