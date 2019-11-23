---
title: CorUnmanagedCallingConvention 列挙型
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 58d30e71929d314ee36adb9f83270858ff8a161b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442440"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="3b32d-102">CorUnmanagedCallingConvention 列挙型</span><span class="sxs-lookup"><span data-stu-id="3b32d-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="3b32d-103">Specifies the calling conventions for unmanaged code.</span><span class="sxs-lookup"><span data-stu-id="3b32d-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b32d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b32d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="3b32d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3b32d-105">Members</span></span>  
  
|<span data-ttu-id="3b32d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3b32d-106">Member</span></span>|<span data-ttu-id="3b32d-107">説明</span><span class="sxs-lookup"><span data-stu-id="3b32d-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="3b32d-108">The C language calling convention.</span><span class="sxs-lookup"><span data-stu-id="3b32d-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="3b32d-109">The standard calling convention.</span><span class="sxs-lookup"><span data-stu-id="3b32d-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="3b32d-110">The "this" calling convention.</span><span class="sxs-lookup"><span data-stu-id="3b32d-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="3b32d-111">The "fast" calling convention.</span><span class="sxs-lookup"><span data-stu-id="3b32d-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="3b32d-112">使用しません。</span><span class="sxs-lookup"><span data-stu-id="3b32d-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="3b32d-113">使用しません。</span><span class="sxs-lookup"><span data-stu-id="3b32d-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="3b32d-114">使用しません。</span><span class="sxs-lookup"><span data-stu-id="3b32d-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="3b32d-115">使用しません。</span><span class="sxs-lookup"><span data-stu-id="3b32d-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b32d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b32d-116">Remarks</span></span>  
 <span data-ttu-id="3b32d-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span><span class="sxs-lookup"><span data-stu-id="3b32d-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b32d-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="3b32d-118">Requirements</span></span>  
 <span data-ttu-id="3b32d-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b32d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b32d-120">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3b32d-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3b32d-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b32d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b32d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b32d-122">See also</span></span>

- [<span data-ttu-id="3b32d-123">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="3b32d-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
