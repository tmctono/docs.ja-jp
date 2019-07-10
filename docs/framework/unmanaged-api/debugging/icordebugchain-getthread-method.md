---
title: ICorDebugChain::GetThread メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05002ecdb903a1adfeea88930083ba472164324
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745637"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="6a080-102">ICorDebugChain::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="6a080-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="6a080-103">この呼び出しチェーンが物理スレッドの一部を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a080-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a080-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a080-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a080-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a080-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="6a080-106">[out]この呼び出しチェーンがの一部に物理スレッドを表す ICorDebugThread オブジェクトへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="6a080-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a080-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a080-107">Requirements</span></span>  
 <span data-ttu-id="6a080-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a080-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a080-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a080-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a080-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a080-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a080-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a080-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
