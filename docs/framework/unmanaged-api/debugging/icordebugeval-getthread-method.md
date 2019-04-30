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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cc5b6e7c6fe44080b35dc07f029ad311b88ca7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989054"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="a8a00-102">ICorDebugEval::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="a8a00-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="a8a00-103">この評価が実行またはが実行スレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8a00-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a00-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8a00-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8a00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8a00-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="a8a00-106">[out]スレッドを表す ICorDebugThread オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8a00-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8a00-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8a00-107">Requirements</span></span>  
 <span data-ttu-id="a8a00-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8a00-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8a00-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8a00-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8a00-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8a00-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8a00-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8a00-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
