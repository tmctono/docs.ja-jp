---
title: ICorDebugProcess2::GetThreadForTaskID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85040a31966a92ead6ca4786f62852f17923056
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736919"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="d5eb1-102">ICorDebugProcess2::GetThreadForTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="d5eb1-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="d5eb1-103">指定した識別子を持つタスクが実行されているスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5eb1-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5eb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5eb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5eb1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5eb1-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="d5eb1-106">[in]タスクの識別子です。</span><span class="sxs-lookup"><span data-stu-id="d5eb1-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="d5eb1-107">[out]取得するスレッドを表す ICorDebugThread2 オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d5eb1-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5eb1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5eb1-108">Remarks</span></span>  
 <span data-ttu-id="d5eb1-109">ホストを使用してタスクの識別子を設定することができます、 [iclrtask::settaskidentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d5eb1-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5eb1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5eb1-110">Requirements</span></span>  
 <span data-ttu-id="d5eb1-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5eb1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5eb1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5eb1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5eb1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5eb1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5eb1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5eb1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
