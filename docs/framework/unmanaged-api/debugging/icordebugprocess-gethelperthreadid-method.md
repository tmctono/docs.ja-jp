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
ms.openlocfilehash: fc4f4b56552c4db265d2ea123a84c7792ad53094
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213635"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="cc0c5-102">ICorDebugProcess::GetHelperThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="cc0c5-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="cc0c5-103">デバッガーの内部ヘルパースレッドのオペレーティングシステム (OS) スレッド ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc0c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc0c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc0c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc0c5-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="cc0c5-106">入出力デバッガーの内部ヘルパースレッドの OS スレッド ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc0c5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cc0c5-107">Remarks</span></span>  
 <span data-ttu-id="cc0c5-108">マネージデバッグおよびアンマネージデバッグ中は、デバッガーによって設定されたブレークポイントにヒットした場合に、指定した ID を持つスレッドが実行された状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="cc0c5-109">デバッガーでは、このスレッドをユーザーに対して非表示にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="cc0c5-110">まだプロセスにヘルパースレッドが存在しない場合、 `GetHelperThreadID` メソッドは \* で0を返し `pThreadID` ます。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="cc0c5-111">ヘルパースレッドのスレッド ID は、時間の経過と共に変更される可能性があるため、キャッシュすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="cc0c5-112">停止イベントが発生するたびにスレッド ID を再照会する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="cc0c5-113">デバッガーのヘルパースレッドのスレッド ID は、すべてのアンマネージコードに対して、すべてのアンマネージ[コールバック:: CreateThread](icordebugmanagedcallback-createthread-method.md)イベントに対して適切になります。これにより、デバッガーはヘルパースレッドのスレッド id を判断し、ユーザーに対して非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="cc0c5-114">アンマネージイベント中にヘルパースレッドとして識別されたスレッド `ICorDebugManagedCallback::CreateThread` は、マネージユーザーコードを実行しません。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc0c5-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="cc0c5-115">Requirements</span></span>  
 <span data-ttu-id="cc0c5-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc0c5-117">**ヘッダー:** CorDebug。</span><span class="sxs-lookup"><span data-stu-id="cc0c5-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="cc0c5-118">CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="cc0c5-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="cc0c5-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc0c5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc0c5-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0c5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
