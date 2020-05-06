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
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860702"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="a3675-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions メソッド</span><span class="sxs-lookup"><span data-stu-id="a3675-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="a3675-103">指定されたメモリ領域を列挙します。</span><span class="sxs-lookup"><span data-stu-id="a3675-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3675-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3675-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3675-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3675-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="a3675-106">から結果をデバッガーに通知するために、列挙される各メモリ領域に対してこのメソッドによって呼び出される[ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3675-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="a3675-107">コールバックがエラーを示す場合でも、メモリ領域の列挙は続行されます。</span><span class="sxs-lookup"><span data-stu-id="a3675-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="a3675-108">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="a3675-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="a3675-109">から列挙するメモリ領域を指定する[Clrdataenummemoryflags](clrdataenummemoryflags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="a3675-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3675-110">解説</span><span class="sxs-lookup"><span data-stu-id="a3675-110">Remarks</span></span>  
 <span data-ttu-id="a3675-111">このメソッドは、指定された[ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)インスタンスを使用して、結果を呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="a3675-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3675-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3675-112">Requirements</span></span>  
 <span data-ttu-id="a3675-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3675-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3675-114">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="a3675-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a3675-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3675-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3675-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3675-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3675-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3675-117">See also</span></span>

- [<span data-ttu-id="a3675-118">ICLRDataEnumMemoryRegions インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3675-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
