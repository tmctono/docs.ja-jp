---
title: ICorDebugFunction2::GetJMCStatus メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137820"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="4c718-102">ICorDebugFunction2::GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="4c718-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="4c718-103">この ICorDebugFunction2 オブジェクトによって表される関数がユーザーコードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4c718-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c718-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c718-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c718-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c718-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="4c718-106">入出力この関数がユーザーコードとしてマークされている場合に `true`されるブール値へのポインター。それ以外の場合、値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="4c718-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c718-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c718-107">Remarks</span></span>  
 <span data-ttu-id="4c718-108">この `ICorDebugFunction2` によって表される関数をデバッグできない場合、`pbIsJustMyCode` は常に `false`されます。</span><span class="sxs-lookup"><span data-stu-id="4c718-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c718-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="4c718-109">Requirements</span></span>  
 <span data-ttu-id="4c718-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c718-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c718-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c718-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c718-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c718-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c718-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c718-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
