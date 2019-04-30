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
ms.openlocfilehash: 4ab2b584b4a3e9bef17110f3084dc93efb2e5167
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989366"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="20c94-102">ICorDebugChain::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="20c94-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="20c94-103">この呼び出しチェーンが物理スレッドの一部を取得します。</span><span class="sxs-lookup"><span data-stu-id="20c94-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c94-104">構文</span><span class="sxs-lookup"><span data-stu-id="20c94-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20c94-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20c94-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="20c94-106">[out]この呼び出しチェーンがの一部に物理スレッドを表す ICorDebugThread オブジェクトへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="20c94-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c94-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="20c94-107">Requirements</span></span>  
 <span data-ttu-id="20c94-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c94-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c94-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20c94-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20c94-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20c94-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20c94-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20c94-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
