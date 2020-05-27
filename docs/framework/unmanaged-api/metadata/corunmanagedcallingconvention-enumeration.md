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
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008951"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="b3ece-102">CorUnmanagedCallingConvention 列挙型</span><span class="sxs-lookup"><span data-stu-id="b3ece-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="b3ece-103">アンマネージコードの呼び出し規約を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3ece-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ece-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3ece-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b3ece-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="b3ece-105">Members</span></span>  
  
|<span data-ttu-id="b3ece-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b3ece-106">Member</span></span>|<span data-ttu-id="b3ece-107">説明</span><span class="sxs-lookup"><span data-stu-id="b3ece-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="b3ece-108">C 言語の呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="b3ece-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="b3ece-109">標準の呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="b3ece-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="b3ece-110">"This" 呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="b3ece-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="b3ece-111">"高速" 呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="b3ece-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="b3ece-112">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="b3ece-113">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="b3ece-114">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="b3ece-115">使用されていません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3ece-116">コメント</span><span class="sxs-lookup"><span data-stu-id="b3ece-116">Remarks</span></span>  
 <span data-ttu-id="b3ece-117">CLR では、.NET Framework バージョン1.0 での "高速" 呼び出し規約はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3ece-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3ece-118">Requirements</span></span>  
 <span data-ttu-id="b3ece-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ece-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ece-120">**ヘッダー:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="b3ece-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b3ece-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ece-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ece-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3ece-122">See also</span></span>

- [<span data-ttu-id="b3ece-123">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="b3ece-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
