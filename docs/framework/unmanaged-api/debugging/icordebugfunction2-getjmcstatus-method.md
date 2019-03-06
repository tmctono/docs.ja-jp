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
ms.openlocfilehash: d23a0a489cfe13201b7798920feb3528db3b0709
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494611"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="68355-102">ICorDebugFunction2::GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="68355-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="68355-103">ICorDebugFunction2 オブジェクトによって表される関数がユーザー コードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="68355-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68355-104">構文</span><span class="sxs-lookup"><span data-stu-id="68355-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68355-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68355-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="68355-106">[out]ブール値へのポインター`true`場合は、この関数がユーザー コードとしてマークされている場合は、値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="68355-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68355-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="68355-107">Remarks</span></span>  
 <span data-ttu-id="68355-108">これによって、関数が表されている場合`ICorDebugFunction2`デバッグできない`pbIsJustMyCode`は常に`false`します。</span><span class="sxs-lookup"><span data-stu-id="68355-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68355-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="68355-109">Requirements</span></span>  
 <span data-ttu-id="68355-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68355-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68355-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68355-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68355-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68355-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68355-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68355-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
