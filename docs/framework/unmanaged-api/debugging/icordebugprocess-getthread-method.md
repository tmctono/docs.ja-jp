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
ms.openlocfilehash: 081852f91f243c4a979e2969220e71bd10c8c56b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212887"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="9074e-102">ICorDebugProcess::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="9074e-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="9074e-103">指定されたオペレーティングシステム (OS) のスレッド ID を持つ、このプロセスのスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9074e-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9074e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9074e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9074e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9074e-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="9074e-106">から取得するスレッドの OS スレッド ID。</span><span class="sxs-lookup"><span data-stu-id="9074e-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="9074e-107">入出力スレッドを表す、スレッドオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9074e-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9074e-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9074e-108">Requirements</span></span>  
 <span data-ttu-id="9074e-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9074e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9074e-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9074e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9074e-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9074e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9074e-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9074e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
