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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67b85917be590bdba7ed3f10972ad39b731dbcdd
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274244"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="dd9d3-102">CLRDataEnumMemoryFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="dd9d3-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="dd9d3-103">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md)メソッドへの呼び出しに含まれるメモリ領域を示します。</span><span class="sxs-lookup"><span data-stu-id="dd9d3-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd9d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd9d3-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="dd9d3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="dd9d3-105">Members</span></span>  
  
|<span data-ttu-id="dd9d3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="dd9d3-106">Member</span></span>|<span data-ttu-id="dd9d3-107">説明</span><span class="sxs-lookup"><span data-stu-id="dd9d3-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="dd9d3-108">ミニダンプ (スパースメモリダンプ)。</span><span class="sxs-lookup"><span data-stu-id="dd9d3-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="dd9d3-109">完全なヒープダンプ。</span><span class="sxs-lookup"><span data-stu-id="dd9d3-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd9d3-110">要件</span><span class="sxs-lookup"><span data-stu-id="dd9d3-110">Requirements</span></span>  
 <span data-ttu-id="dd9d3-111">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9d3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd9d3-112">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="dd9d3-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dd9d3-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="dd9d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd9d3-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd9d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9d3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd9d3-115">See also</span></span>

- [<span data-ttu-id="dd9d3-116">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="dd9d3-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
