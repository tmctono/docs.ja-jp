---
title: ICorDebugThread::GetUserState メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4deaa3ab4b14fbd32d45841966cfac9e33b9f31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487851"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="cbdfb-102">ICorDebugThread::GetUserState メソッド</span><span class="sxs-lookup"><span data-stu-id="cbdfb-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="cbdfb-103">この ICorDebugThread の現在のユーザー状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="cbdfb-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbdfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbdfb-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbdfb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbdfb-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="cbdfb-106">[out]このスレッドの現在のユーザー状態を記述する CorDebugUserState 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cbdfb-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbdfb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbdfb-107">Remarks</span></span>  
 <span data-ttu-id="cbdfb-108">スレッドのユーザーの状態は、デバッグ中にプログラムでチェックするときに、スレッドの状態です。</span><span class="sxs-lookup"><span data-stu-id="cbdfb-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="cbdfb-109">スレッドは、複数の状態ビットが設定があります。</span><span class="sxs-lookup"><span data-stu-id="cbdfb-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbdfb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbdfb-110">Requirements</span></span>  
 <span data-ttu-id="cbdfb-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbdfb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbdfb-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbdfb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbdfb-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbdfb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbdfb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbdfb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
