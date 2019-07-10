---
title: CorDebugBlockingReason 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ea71439c9a6c494c218a7cfc18508f4f8173b03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740386"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="a00d6-102">CorDebugBlockingReason 列挙体</span><span class="sxs-lookup"><span data-stu-id="a00d6-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="a00d6-103">指定されたオブジェクト上でスレッドがブロックされる理由を指定します。</span><span class="sxs-lookup"><span data-stu-id="a00d6-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="a00d6-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="a00d6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a00d6-105">Members</span></span>  
  
|<span data-ttu-id="a00d6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a00d6-106">Member</span></span>|<span data-ttu-id="a00d6-107">説明</span><span class="sxs-lookup"><span data-stu-id="a00d6-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="a00d6-108">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="a00d6-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="a00d6-109">スレッドがクリティカル セクションに関連付けられたオブジェクトのモニター ロックを取得しようとしています。</span><span class="sxs-lookup"><span data-stu-id="a00d6-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="a00d6-110">通常の 1 つを呼び出すときに発生、<xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>または<xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a00d6-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="a00d6-111">スレッドは、オブジェクトのモニター ロックに関連付けられているイベントを待機しています。</span><span class="sxs-lookup"><span data-stu-id="a00d6-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="a00d6-112">通常の 1 つを呼び出すときに発生、 <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait`メソッド。</span><span class="sxs-lookup"><span data-stu-id="a00d6-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a00d6-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="a00d6-113">Remarks</span></span>  
 <span data-ttu-id="a00d6-114">ときに、`BLOCKING_MONITOR_CRITICAL_SECTION`または`BLOCKING_MONITOR_EVENT`でメンバーが使用される、 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造、`pBlockingObject`構造体の指すが入力されているオブジェクトを表す"ICorDebugValue"インターフェイスのメンバー.</span><span class="sxs-lookup"><span data-stu-id="a00d6-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="a00d6-115">実装も必ず、 [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a00d6-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00d6-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="a00d6-116">Requirements</span></span>  
 <span data-ttu-id="a00d6-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a00d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00d6-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a00d6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a00d6-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a00d6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a00d6-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00d6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00d6-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a00d6-121">See also</span></span>

- [<span data-ttu-id="a00d6-122">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="a00d6-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="a00d6-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a00d6-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
