---
title: ICorDebugProcess::GetThread メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
ms.openlocfilehash: 6bf73a4be40f1fbd8e9d37477907001604e8e4a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128815"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="af6f5-102">ICorDebugProcess::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="af6f5-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="af6f5-103">指定されたオペレーティングシステム (OS) のスレッド ID を持つ、このプロセスのスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="af6f5-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af6f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="af6f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af6f5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af6f5-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="af6f5-106">から取得するスレッドの OS スレッド ID。</span><span class="sxs-lookup"><span data-stu-id="af6f5-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="af6f5-107">入出力スレッドを表す、スレッドオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="af6f5-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af6f5-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="af6f5-108">Requirements</span></span>  
 <span data-ttu-id="af6f5-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af6f5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af6f5-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af6f5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af6f5-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af6f5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af6f5-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af6f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
