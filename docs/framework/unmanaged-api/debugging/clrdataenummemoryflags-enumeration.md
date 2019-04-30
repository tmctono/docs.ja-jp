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
ms.openlocfilehash: 80ea3afef4aee51760e3a2ce6a2b895bca4a6ec5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961370"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="c8f7c-102">CLRDataEnumMemoryFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="c8f7c-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="c8f7c-103">メモリ領域への呼び出しを示す、 [iclrdataenummemoryregions::enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)メソッドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f7c-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f7c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8f7c-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c8f7c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8f7c-105">Members</span></span>  
  
|<span data-ttu-id="c8f7c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8f7c-106">Member</span></span>|<span data-ttu-id="c8f7c-107">説明</span><span class="sxs-lookup"><span data-stu-id="c8f7c-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="c8f7c-108">ミニダンプの場合、スパースのメモリ ダンプは、します。</span><span class="sxs-lookup"><span data-stu-id="c8f7c-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="c8f7c-109">完全なヒープ ダンプします。</span><span class="sxs-lookup"><span data-stu-id="c8f7c-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8f7c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8f7c-110">Requirements</span></span>  
 <span data-ttu-id="c8f7c-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f7c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8f7c-112">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c8f7c-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c8f7c-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8f7c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8f7c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8f7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f7c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8f7c-115">See also</span></span>

- [<span data-ttu-id="c8f7c-116">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="c8f7c-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
