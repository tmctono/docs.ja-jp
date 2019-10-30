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
ms.openlocfilehash: d731b12ddf195137ff38d32ab0ca52aa90f48d4e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132779"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="b1ae9-102">CorDebugJITCompilerFlagsDeprecated 列挙型</span><span class="sxs-lookup"><span data-stu-id="b1ae9-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="b1ae9-103">この列挙型は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="b1ae9-103">This enumeration is obsolete.</span></span> <span data-ttu-id="b1ae9-104">代わりに、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)列挙体の `CORDEBUG_JIT_DEFAULT` メンバーを使用してください。</span><span class="sxs-lookup"><span data-stu-id="b1ae9-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ae9-105">構文</span><span class="sxs-lookup"><span data-stu-id="b1ae9-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="b1ae9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="b1ae9-106">Members</span></span>  
  
|<span data-ttu-id="b1ae9-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="b1ae9-107">Member</span></span>|<span data-ttu-id="b1ae9-108">説明</span><span class="sxs-lookup"><span data-stu-id="b1ae9-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="b1ae9-109">代わりに、`CORDEBUG_JIT_DEFAULT` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b1ae9-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1ae9-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="b1ae9-110">Requirements</span></span>  
 <span data-ttu-id="b1ae9-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ae9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1ae9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1ae9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1ae9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1ae9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1ae9-114">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="b1ae9-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ae9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1ae9-115">See also</span></span>

- [<span data-ttu-id="b1ae9-116">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="b1ae9-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
