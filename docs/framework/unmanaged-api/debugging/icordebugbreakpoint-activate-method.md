---
title: ICorDebugBreakpoint::Activate メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
ms.openlocfilehash: 24dc55cc9a49c3602829ca627d584c761b4088ce
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894747"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="a46d7-102">ICorDebugBreakpoint::Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="a46d7-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="a46d7-103">この`ICorDebugBreakpoint`のアクティブな状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="a46d7-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a46d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a46d7-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a46d7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a46d7-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="a46d7-106">から状態をアクティブと`true`して指定するには、この値をに設定します。それ以外の場合は、 `false`この値をに設定します。</span><span class="sxs-lookup"><span data-stu-id="a46d7-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a46d7-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a46d7-107">Requirements</span></span>  
 <span data-ttu-id="a46d7-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46d7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a46d7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a46d7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a46d7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a46d7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a46d7-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a46d7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
