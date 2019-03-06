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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5df5bed730211676acc4770c91cc6551bde0179b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57464725"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="b970c-102">ICorDebugBreakpoint::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="b970c-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="b970c-103">示す値を取得するかどうかこの`ICorDebugBreakpoint`がアクティブです。</span><span class="sxs-lookup"><span data-stu-id="b970c-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b970c-104">構文</span><span class="sxs-lookup"><span data-stu-id="b970c-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b970c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b970c-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="b970c-106">[out]`true`このブレークポイントがアクティブな。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="b970c-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b970c-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b970c-107">Requirements</span></span>  
 <span data-ttu-id="b970c-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b970c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b970c-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b970c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b970c-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b970c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b970c-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b970c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
