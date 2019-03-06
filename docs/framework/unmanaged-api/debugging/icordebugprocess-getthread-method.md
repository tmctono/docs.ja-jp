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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36070d5374a11daf4b7800481c86d61057989631
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470079"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="d8e06-102">ICorDebugProcess::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="d8e06-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="d8e06-103">指定したオペレーティング システム (OS) のスレッド ID を持つこのプロセスのスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8e06-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e06-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8e06-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8e06-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8e06-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="d8e06-106">[in]OS スレッドのスレッドの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8e06-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="d8e06-107">[out]スレッドを表す ICorDebugThread オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d8e06-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8e06-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8e06-108">Requirements</span></span>  
 <span data-ttu-id="d8e06-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e06-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8e06-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8e06-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8e06-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8e06-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8e06-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8e06-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
