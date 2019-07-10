---
title: ICorDebugThread2::GetTaskID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1272df17a9a9a500b84f62914811b8d109bf3cdd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768955"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="dc170-102">ICorDebugThread2::GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="dc170-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="dc170-103">このスレッドで実行されているタスクの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc170-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc170-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc170-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc170-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc170-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="dc170-106">[out]この ICorDebugThread2 オブジェクトによって表されるスレッドで実行中のタスクの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc170-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc170-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc170-107">Remarks</span></span>  
 <span data-ttu-id="dc170-108">スレッドが、接続に関連付けられた場合、タスクはのみ、スレッドで実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc170-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="dc170-109">`GetTaskID` 0 が返されます`pTaskId`スレッドは、接続に関連付けられていない場合。</span><span class="sxs-lookup"><span data-stu-id="dc170-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc170-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc170-110">Requirements</span></span>  
 <span data-ttu-id="dc170-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc170-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc170-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc170-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc170-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc170-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc170-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc170-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
