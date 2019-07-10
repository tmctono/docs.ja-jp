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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f056e4ae233e70223755c1961cd3ee5da68ec90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745180"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="8a51a-102">ICorDebugBreakpoint::Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="8a51a-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="8a51a-103">このアクティブな状態を設定`ICorDebugBreakpoint`します。</span><span class="sxs-lookup"><span data-stu-id="8a51a-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a51a-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a51a-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a51a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a51a-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="8a51a-106">[in]この値に設定`true`; アクティブな状態を指定する場合は、この値に設定`false`。</span><span class="sxs-lookup"><span data-stu-id="8a51a-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a51a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a51a-107">Requirements</span></span>  
 <span data-ttu-id="8a51a-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a51a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a51a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a51a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a51a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a51a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a51a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a51a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
