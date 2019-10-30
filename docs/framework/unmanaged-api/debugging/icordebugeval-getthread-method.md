---
title: ICorDebugEval::GetThread メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: 6a7d9465a454175b58bb7b9566d31f3c65420610
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085054"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="9a1c7-102">ICorDebugEval::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="9a1c7-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="9a1c7-103">この評価が実行されている、または実行されるスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a1c7-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a1c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a1c7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a1c7-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="9a1c7-106">入出力スレッドを表す、スレッドオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9a1c7-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a1c7-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="9a1c7-107">Requirements</span></span>  
 <span data-ttu-id="9a1c7-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a1c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a1c7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a1c7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a1c7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a1c7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a1c7-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a1c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
