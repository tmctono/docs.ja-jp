---
title: CorDebugJITCompilerFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66a8ba59d221bb3fa2e815a1cbcfa79c474666cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105470"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="9c7ac-102">CorDebugJITCompilerFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="9c7ac-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="9c7ac-103">マネージド Just-In-Time (JIT) コンパイラの動作に影響を与える値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c7ac-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c7ac-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9c7ac-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9c7ac-105">Members</span></span>  
  
|<span data-ttu-id="9c7ac-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9c7ac-106">Member</span></span>|<span data-ttu-id="9c7ac-107">説明</span><span class="sxs-lookup"><span data-stu-id="9c7ac-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="9c7ac-108">コンパイラがコンパイルのデータを追跡し、により、最適化を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c7ac-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="9c7ac-109">コンパイラが最適化を無効にしますが、コンパイルのデータを追跡する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c7ac-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="9c7ac-110">コンパイラを追跡するコンパイルのデータの最適化を無効にしてエディット コンティニュのテクノロジを有効に指定します。</span><span class="sxs-lookup"><span data-stu-id="9c7ac-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c7ac-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c7ac-111">Requirements</span></span>  
 <span data-ttu-id="9c7ac-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c7ac-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c7ac-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c7ac-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c7ac-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c7ac-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9c7ac-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9c7ac-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c7ac-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c7ac-116">See also</span></span>

- [<span data-ttu-id="9c7ac-117">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="9c7ac-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
