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
ms.openlocfilehash: 417f99c2b9fa7e77f8696c27cb3929c92956c08c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946344"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="cf710-102">ICorDebugThread2::GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="cf710-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="cf710-103">このスレッドで実行されているタスクの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cf710-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf710-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf710-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf710-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf710-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="cf710-106">[out]この ICorDebugThread2 オブジェクトによって表されるスレッドで実行中のタスクの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf710-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf710-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf710-107">Remarks</span></span>  
 <span data-ttu-id="cf710-108">スレッドが、接続に関連付けられた場合、タスクはのみ、スレッドで実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf710-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="cf710-109">`GetTaskID` 0 が返されます`pTaskId`スレッドは、接続に関連付けられていない場合。</span><span class="sxs-lookup"><span data-stu-id="cf710-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf710-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf710-110">Requirements</span></span>  
 <span data-ttu-id="cf710-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf710-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf710-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf710-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf710-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf710-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf710-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf710-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
