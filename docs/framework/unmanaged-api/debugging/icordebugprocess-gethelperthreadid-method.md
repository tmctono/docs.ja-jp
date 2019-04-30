---
title: ICorDebugProcess::GetHelperThreadID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd5e30d08e667dcd5a8be1f9502462f28290068e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987741"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="45aa9-102">ICorDebugProcess::GetHelperThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="45aa9-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="45aa9-103">デバッガーの内部ヘルパーのスレッドのオペレーティング システム (OS) のスレッド ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="45aa9-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45aa9-104">構文</span><span class="sxs-lookup"><span data-stu-id="45aa9-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45aa9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45aa9-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="45aa9-106">[out]OS へのポインターはスレッド、デバッガーの内部ヘルパーのスレッドの ID です。</span><span class="sxs-lookup"><span data-stu-id="45aa9-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45aa9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="45aa9-107">Remarks</span></span>  
 <span data-ttu-id="45aa9-108">マネージ コードとアンマネージ デバッグ中は、デバッガーでブレークポイントにヒットした場合、指定した ID を持つスレッド引き続き実行されているようにする、デバッガーの責任です。</span><span class="sxs-lookup"><span data-stu-id="45aa9-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="45aa9-109">デバッガーは、ユーザーからは、このスレッドを非表示にする可能性がありますも。</span><span class="sxs-lookup"><span data-stu-id="45aa9-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="45aa9-110">ヘルパーのスレッドが存在しない場合、プロセスで、まだ、`GetHelperThreadID`にゼロが返される \*`pThreadID`します。</span><span class="sxs-lookup"><span data-stu-id="45aa9-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="45aa9-111">時間の経過と共に変更可能性がありますので、ヘルパーのスレッドのスレッド ID をキャッシュすることはできません。</span><span class="sxs-lookup"><span data-stu-id="45aa9-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="45aa9-112">停止イベントごとにスレッド ID を再クエリする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45aa9-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="45aa9-113">なければ、デバッガーのヘルパーのスレッドのスレッド ID すべてアンマネージ[icordebugmanagedcallback::createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)イベント、ため、デバッガー ヘルパー スレッドのスレッド ID を特定し、ユーザーから非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="45aa9-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="45aa9-114">アンマネージの中にヘルパー スレッドとして識別されるスレッド`ICorDebugManagedCallback::CreateThread`イベントではマネージ ユーザー コードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="45aa9-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45aa9-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="45aa9-115">Requirements</span></span>  
 <span data-ttu-id="45aa9-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45aa9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45aa9-117">**ヘッダー:** CorDebug.idl します。</span><span class="sxs-lookup"><span data-stu-id="45aa9-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="45aa9-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45aa9-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="45aa9-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45aa9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45aa9-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45aa9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
