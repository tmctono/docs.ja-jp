---
title: CorDebugPlatform 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989639"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="bff13-102">CorDebugPlatform 列挙型</span><span class="sxs-lookup"><span data-stu-id="bff13-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="bff13-103">使用されるターゲット プラットフォームの値を提供します、 [icordebugdatatarget::getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="bff13-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff13-104">構文</span><span class="sxs-lookup"><span data-stu-id="bff13-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="bff13-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="bff13-105">Members</span></span>  
  
|<span data-ttu-id="bff13-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="bff13-106">Member</span></span>|<span data-ttu-id="bff13-107">説明</span><span class="sxs-lookup"><span data-stu-id="bff13-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bff13-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="bff13-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="bff13-109">ターゲット プラットフォームは、Intel x86 ハードウェア上で稼動する Windows です。</span><span class="sxs-lookup"><span data-stu-id="bff13-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="bff13-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="bff13-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="bff13-111">ターゲット プラットフォームは、AMD64 または Intel EM64T ハードウェア上で稼動する 64 ビット Windows です。</span><span class="sxs-lookup"><span data-stu-id="bff13-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="bff13-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="bff13-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="bff13-113">ターゲット プラットフォームは、Intel IA-64 ハードウェア上で稼動する 32 ビット Windows です。</span><span class="sxs-lookup"><span data-stu-id="bff13-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="bff13-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="bff13-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="bff13-115">ターゲット プラットフォームは、PowerPC ハードウェア上で稼動する Macintosh オペレーティング システムです。</span><span class="sxs-lookup"><span data-stu-id="bff13-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="bff13-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="bff13-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="bff13-117">ターゲット プラットフォームは、Intel x86 ハードウェア上で稼動する Macintosh オペレーティング システムです。</span><span class="sxs-lookup"><span data-stu-id="bff13-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="bff13-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="bff13-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="bff13-119">ターゲット プラットフォームは、Windows ARM ハードウェア上で稼動する Macintosh オペレーティング システムです。</span><span class="sxs-lookup"><span data-stu-id="bff13-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="bff13-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="bff13-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="bff13-121">ターゲット プラットフォームは、amd 64 ハードウェアで実行されている Macintosh オペレーティング システムです。</span><span class="sxs-lookup"><span data-stu-id="bff13-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bff13-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="bff13-122">Requirements</span></span>  
 <span data-ttu-id="bff13-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff13-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bff13-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bff13-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bff13-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bff13-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bff13-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bff13-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="bff13-127">`CORDB_PLATFORM_WINDOWS_ARM` および `CORDB_PLATFORM_MAC_AMD64` メンバーは、.NET Framework 4.5.2 以降のバージョンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bff13-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff13-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="bff13-128">See also</span></span>

- [<span data-ttu-id="bff13-129">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="bff13-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
