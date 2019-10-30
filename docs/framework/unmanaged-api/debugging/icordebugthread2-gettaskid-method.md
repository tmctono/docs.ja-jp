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
ms.openlocfilehash: d5f2838007504e56ad44614a6778083be046629f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140074"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="f637c-102">ICorDebugThread2::GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="f637c-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="f637c-103">このスレッドで実行されているタスクの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="f637c-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f637c-104">構文</span><span class="sxs-lookup"><span data-stu-id="f637c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f637c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f637c-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="f637c-106">入出力この ICorDebugThread2 オブジェクトによって表されるスレッド上で実行されているタスクの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f637c-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f637c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f637c-107">Remarks</span></span>  
 <span data-ttu-id="f637c-108">スレッドが接続に関連付けられている場合にのみ、スレッドでタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f637c-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="f637c-109">スレッドが接続に関連付けられていない場合、`GetTaskID` は `pTaskId` で0を返します。</span><span class="sxs-lookup"><span data-stu-id="f637c-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f637c-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="f637c-110">Requirements</span></span>  
 <span data-ttu-id="f637c-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f637c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f637c-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f637c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f637c-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f637c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f637c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f637c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
