---
title: ICorDebugThread::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
ms.openlocfilehash: 8928e22b70af0360660c30289ee999a3e4c5e99e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133468"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="2da51-102">ICorDebugThread::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="2da51-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="2da51-103">このコンポーネントがパートを形成するプロセスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2da51-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da51-104">構文</span><span class="sxs-lookup"><span data-stu-id="2da51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2da51-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2da51-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="2da51-106">入出力プロセスを表す、のプロセスインターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2da51-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2da51-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="2da51-107">Requirements</span></span>  
 <span data-ttu-id="2da51-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2da51-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2da51-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2da51-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2da51-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2da51-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2da51-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2da51-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
