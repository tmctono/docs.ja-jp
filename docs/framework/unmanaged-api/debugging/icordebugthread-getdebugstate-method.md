---
title: ICorDebugThread::GetDebugState メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0baabbb736365b138d1754e68070207b4310bf57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762453"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="7c6f5-102">ICorDebugThread::GetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="7c6f5-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="7c6f5-103">この ICorDebugThread オブジェクトの現在のデバッグ状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="7c6f5-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c6f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c6f5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c6f5-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="7c6f5-106">[out]このスレッドの現在のデバッグ状態を説明する CorDebugThreadState 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7c6f5-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c6f5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c6f5-107">Remarks</span></span>  
 <span data-ttu-id="7c6f5-108">プロセスが現在停止している場合`pState`プロセスに続く、このスレッドの実際の現在状態にない場合は、このスレッドの存在のデバッグ状態を表します。</span><span class="sxs-lookup"><span data-stu-id="7c6f5-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c6f5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c6f5-109">Requirements</span></span>  
 <span data-ttu-id="7c6f5-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c6f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c6f5-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c6f5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c6f5-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c6f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c6f5-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c6f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
