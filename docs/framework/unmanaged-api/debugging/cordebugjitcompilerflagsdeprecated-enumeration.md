---
title: CorDebugJITCompilerFlagsDeprecated 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd0def06defa677ddde798106c299ed909cd4ce1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739791"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="eedea-102">CorDebugJITCompilerFlagsDeprecated 列挙型</span><span class="sxs-lookup"><span data-stu-id="eedea-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="eedea-103">この列挙体は廃止されています。</span><span class="sxs-lookup"><span data-stu-id="eedea-103">This enumeration is obsolete.</span></span> <span data-ttu-id="eedea-104">使用して、`CORDEBUG_JIT_DEFAULT`のメンバー、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)列挙代わりにします。</span><span class="sxs-lookup"><span data-stu-id="eedea-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eedea-105">構文</span><span class="sxs-lookup"><span data-stu-id="eedea-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="eedea-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="eedea-106">Members</span></span>  
  
|<span data-ttu-id="eedea-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="eedea-107">Member</span></span>|<span data-ttu-id="eedea-108">説明</span><span class="sxs-lookup"><span data-stu-id="eedea-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="eedea-109">代わりに、`CORDEBUG_JIT_DEFAULT` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="eedea-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eedea-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="eedea-110">Requirements</span></span>  
 <span data-ttu-id="eedea-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eedea-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eedea-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eedea-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eedea-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eedea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eedea-114">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="eedea-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedea-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eedea-115">See also</span></span>

- [<span data-ttu-id="eedea-116">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="eedea-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
