---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886f78a0561ebbd5470b7932123f67975d650693
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698266"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="20f56-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions メソッド</span><span class="sxs-lookup"><span data-stu-id="20f56-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="20f56-103">指定されたメモリ領域を列挙します。</span><span class="sxs-lookup"><span data-stu-id="20f56-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f56-104">構文</span><span class="sxs-lookup"><span data-stu-id="20f56-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20f56-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20f56-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="20f56-106">[in]ポインター、 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)の結果をデバッガーに通知に列挙されている各メモリ領域には、このメソッドによって呼び出されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="20f56-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="20f56-107">コールバックが障害を示している場合でも、メモリ領域の列挙が続行されます。</span><span class="sxs-lookup"><span data-stu-id="20f56-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="20f56-108">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="20f56-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="20f56-109">[in]値、 [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)を列挙するメモリの領域を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="20f56-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20f56-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="20f56-110">Remarks</span></span>  
 <span data-ttu-id="20f56-111">このメソッドを使用して、指定した[ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)インスタンスの結果の呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="20f56-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20f56-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="20f56-112">Requirements</span></span>  
 <span data-ttu-id="20f56-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20f56-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f56-114">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="20f56-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="20f56-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20f56-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20f56-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f56-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f56-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="20f56-117">See also</span></span>

- [<span data-ttu-id="20f56-118">ICLRDataEnumMemoryRegions インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20f56-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
