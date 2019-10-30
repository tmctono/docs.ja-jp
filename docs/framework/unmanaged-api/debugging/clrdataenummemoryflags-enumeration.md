---
title: CLRDataEnumMemoryFlags 列挙型
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
ms.openlocfilehash: 769e63ac6e23ae0264b79a1cd8d6e3cc1ac5a744
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132404"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="6e7fe-102">CLRDataEnumMemoryFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="6e7fe-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="6e7fe-103">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md)メソッドへの呼び出しに含まれるメモリ領域を示します。</span><span class="sxs-lookup"><span data-stu-id="6e7fe-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e7fe-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6e7fe-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e7fe-105">Members</span></span>  
  
|<span data-ttu-id="6e7fe-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e7fe-106">Member</span></span>|<span data-ttu-id="6e7fe-107">説明</span><span class="sxs-lookup"><span data-stu-id="6e7fe-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="6e7fe-108">ミニダンプ (スパースメモリダンプ)。</span><span class="sxs-lookup"><span data-stu-id="6e7fe-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="6e7fe-109">完全なヒープダンプ。</span><span class="sxs-lookup"><span data-stu-id="6e7fe-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e7fe-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="6e7fe-110">Requirements</span></span>  
 <span data-ttu-id="6e7fe-111">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e7fe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e7fe-112">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="6e7fe-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6e7fe-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e7fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e7fe-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e7fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e7fe-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e7fe-115">See also</span></span>

- [<span data-ttu-id="6e7fe-116">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="6e7fe-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
