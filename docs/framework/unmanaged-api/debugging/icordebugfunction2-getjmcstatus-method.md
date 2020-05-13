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
ms.openlocfilehash: 56dc5f87b32b3aaa0bfbb69541d5a01ae26606ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213236"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="e5d63-102">ICorDebugFunction2::GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="e5d63-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="e5d63-103">この ICorDebugFunction2 オブジェクトによって表される関数がユーザーコードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5d63-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d63-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5d63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5d63-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5d63-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="e5d63-106">入出力`true`この関数がユーザーコードとしてマークされている場合は、ブール値へのポインター。それ以外の場合は、値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="e5d63-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5d63-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5d63-107">Remarks</span></span>  
 <span data-ttu-id="e5d63-108">このによって表される関数を `ICorDebugFunction2` デバッグできない場合、 `pbIsJustMyCode` は常にになり `false` ます。</span><span class="sxs-lookup"><span data-stu-id="e5d63-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d63-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5d63-109">Requirements</span></span>  
 <span data-ttu-id="e5d63-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5d63-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d63-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5d63-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5d63-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5d63-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5d63-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d63-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
