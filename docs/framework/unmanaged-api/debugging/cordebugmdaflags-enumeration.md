---
title: CorDebugMDAFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9f7f3d3419efc9e1dc7d75fc7272432c0cf5d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739696"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="e029e-102">CorDebugMDAFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="e029e-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="e029e-103">マネージド デバッグ アシスタント (MDA) が生成されるスレッドのステータスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e029e-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e029e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e029e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e029e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e029e-105">Members</span></span>  
  
|<span data-ttu-id="e029e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e029e-106">Member</span></span>|<span data-ttu-id="e029e-107">説明</span><span class="sxs-lookup"><span data-stu-id="e029e-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="e029e-108">MDA が起動されたので、MDA が起動されたスレッドが変更されました。</span><span class="sxs-lookup"><span data-stu-id="e029e-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e029e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e029e-109">Remarks</span></span>  
 <span data-ttu-id="e029e-110">呼び出し履歴では、この MDA が最初に発生した場所記述されていない、ときに、スレッドが持つと見なされます*スリップ*します。</span><span class="sxs-lookup"><span data-stu-id="e029e-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="e029e-111">これは、異常終了時に無効な操作のスレッドの実行によってもたらさです。</span><span class="sxs-lookup"><span data-stu-id="e029e-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e029e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e029e-112">Requirements</span></span>  
 <span data-ttu-id="e029e-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e029e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e029e-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e029e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e029e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e029e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e029e-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e029e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e029e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e029e-117">See also</span></span>

- [<span data-ttu-id="e029e-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="e029e-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
