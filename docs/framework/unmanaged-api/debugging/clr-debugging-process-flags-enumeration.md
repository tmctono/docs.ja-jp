---
title: CLR_DEBUGGING_PROCESS_FLAGS 列挙体
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274112"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="6e0c7-102">CLR_DEBUGGING_PROCESS_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="6e0c7-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="6e0c7-103">[ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)メソッドによって使用される値を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e0c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e0c7-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6e0c7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e0c7-105">Members</span></span>  
  
|<span data-ttu-id="6e0c7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e0c7-106">Member</span></span>|<span data-ttu-id="6e0c7-107">説明</span><span class="sxs-lookup"><span data-stu-id="6e0c7-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="6e0c7-108">このランタイムには、送信するキャッチアップマネージデバッガーイベントがありません。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="6e0c7-109">キャッチアップイベントと非キャッチアップイベントの違いについては、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="6e0c7-110">保留中のマネージイベントは<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 、要求です。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e0c7-111">コメント</span><span class="sxs-lookup"><span data-stu-id="6e0c7-111">Remarks</span></span>  
 <span data-ttu-id="6e0c7-112">キャッチアップイベントには、プロセスにアタッチした後にデバッガーが現在の状態になるようにするプロセス、アプリケーションドメイン、アセンブリ、モジュール、スレッド作成通知が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="6e0c7-113">`CLR_DEBUGGING_MANAGED_EVENT_PENDING`フラグによって示されるキャッチアップ以外のイベントには、例外やマネージデバッグアシスタント (MDA) 通知など、他のすべてのデバッガーイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="6e0c7-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`フラグにより、ランタイムは、終了した例外と、キャンセル可能なマネージデバッガーをアタッチする要求を区別できます。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e0c7-115">要件</span><span class="sxs-lookup"><span data-stu-id="6e0c7-115">Requirements</span></span>  
 <span data-ttu-id="6e0c7-116">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e0c7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e0c7-117">**ヘッダー:** メタホスト .idl、メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="6e0c7-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="6e0c7-118">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="6e0c7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e0c7-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e0c7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e0c7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e0c7-120">See also</span></span>

- [<span data-ttu-id="6e0c7-121">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="6e0c7-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="6e0c7-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6e0c7-122">Debugging</span></span>](index.md)
