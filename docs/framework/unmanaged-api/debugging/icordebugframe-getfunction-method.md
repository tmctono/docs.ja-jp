---
title: ICorDebugFrame::GetFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 39175e338e4fd98dd4af1325138da732ed81c764
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137921"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="95090-102">ICorDebugFrame::GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="95090-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="95090-103">このスタックフレームに関連付けられているコードを格納している関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="95090-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95090-104">構文</span><span class="sxs-lookup"><span data-stu-id="95090-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95090-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95090-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="95090-106">入出力このスタックフレームに関連付けられているコードを格納している関数を表す、オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="95090-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95090-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="95090-107">Remarks</span></span>  
 <span data-ttu-id="95090-108">フレームが特定の関数に関連付けられていない場合、`GetFunction` メソッドは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95090-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95090-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="95090-109">Requirements</span></span>  
 <span data-ttu-id="95090-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95090-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95090-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95090-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95090-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95090-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95090-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95090-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
