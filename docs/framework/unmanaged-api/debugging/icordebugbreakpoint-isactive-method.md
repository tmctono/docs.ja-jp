---
title: ICorDebugBreakpoint::IsActive メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 8df4e1df7836f340bb04fc47d1ca55e0fb7c9f0e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122766"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="b7c4b-102">ICorDebugBreakpoint::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="b7c4b-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="b7c4b-103">この `ICorDebugBreakpoint` がアクティブかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7c4b-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7c4b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7c4b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7c4b-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="b7c4b-106">[out] このブレークポイントがアクティブである場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="b7c4b-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7c4b-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="b7c4b-107">Requirements</span></span>  
 <span data-ttu-id="b7c4b-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c4b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7c4b-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7c4b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7c4b-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7c4b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7c4b-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c4b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
