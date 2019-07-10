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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2364c7c47aed1430a86aeee3daabf6b94cbf3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754481"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="66864-102">ICorDebugFunction2::GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="66864-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="66864-103">ICorDebugFunction2 オブジェクトによって表される関数がユーザー コードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="66864-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66864-104">構文</span><span class="sxs-lookup"><span data-stu-id="66864-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66864-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66864-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="66864-106">[out]ブール値へのポインター`true`場合は、この関数がユーザー コードとしてマークされている場合は、値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="66864-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66864-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="66864-107">Remarks</span></span>  
 <span data-ttu-id="66864-108">これによって、関数が表されている場合`ICorDebugFunction2`デバッグできない`pbIsJustMyCode`は常に`false`します。</span><span class="sxs-lookup"><span data-stu-id="66864-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66864-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="66864-109">Requirements</span></span>  
 <span data-ttu-id="66864-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66864-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66864-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66864-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66864-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66864-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66864-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66864-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
