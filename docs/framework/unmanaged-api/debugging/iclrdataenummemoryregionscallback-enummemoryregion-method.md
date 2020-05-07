---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
ms.openlocfilehash: e4fa0a3745200d39a468292e9520b1aeb0e9f1b2
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860667"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="47e0c-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion メソッド</span><span class="sxs-lookup"><span data-stu-id="47e0c-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="47e0c-103">指定されたメモリ領域を列挙しようとした結果をデバッガーに報告するために、 [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md)によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="47e0c-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47e0c-104">構文</span><span class="sxs-lookup"><span data-stu-id="47e0c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47e0c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47e0c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="47e0c-106">から列挙されたメモリ領域の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="47e0c-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="47e0c-107">からメモリ領域のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47e0c-108">解説</span><span class="sxs-lookup"><span data-stu-id="47e0c-108">Remarks</span></span>  
 <span data-ttu-id="47e0c-109">メソッド`ICLRDataEnumMemoryRegions::EnumMemoryRegions`は、メモリ領域を列挙するたびに、このコールバックメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="47e0c-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="47e0c-110">このメソッドがエラーを示す HRESULT を返す場合でも、列挙は続行されます。</span><span class="sxs-lookup"><span data-stu-id="47e0c-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="47e0c-111">このコールバックによって報告されたリージョンが重複しているか、重複している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47e0c-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47e0c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="47e0c-112">Requirements</span></span>  
 <span data-ttu-id="47e0c-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e0c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47e0c-114">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="47e0c-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="47e0c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47e0c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47e0c-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47e0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e0c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="47e0c-117">See also</span></span>

- [<span data-ttu-id="47e0c-118">ICLRDataEnumMemoryRegionsCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="47e0c-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
