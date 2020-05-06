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
ms.openlocfilehash: 7b8a726cffcc00d7371675192a209b2d8e9db94d
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795782"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="decd9-102">CorDebugJITCompilerFlagsDeprecated 列挙型</span><span class="sxs-lookup"><span data-stu-id="decd9-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="decd9-103">この列挙型は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="decd9-103">This enumeration is obsolete.</span></span> <span data-ttu-id="decd9-104">代わりに、 `CORDEBUG_JIT_DEFAULT` [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)列挙体のメンバーを使用してください。</span><span class="sxs-lookup"><span data-stu-id="decd9-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="decd9-105">構文</span><span class="sxs-lookup"><span data-stu-id="decd9-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="decd9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="decd9-106">Members</span></span>  
  
|<span data-ttu-id="decd9-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="decd9-107">Member</span></span>|<span data-ttu-id="decd9-108">説明</span><span class="sxs-lookup"><span data-stu-id="decd9-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="decd9-109">代わりに `CORDEBUG_JIT_DEFAULT` を使用してください</span><span class="sxs-lookup"><span data-stu-id="decd9-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="decd9-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="decd9-110">Requirements</span></span>  
 <span data-ttu-id="decd9-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="decd9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="decd9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="decd9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="decd9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="decd9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="decd9-114">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="decd9-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="decd9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="decd9-115">See also</span></span>

- [<span data-ttu-id="decd9-116">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="decd9-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
