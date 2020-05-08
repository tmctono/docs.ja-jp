---
title: ICorDebugChain::GetCaller メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: a6d26924773e6ad505975402ec3ace150d02cc3a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894615"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="18cdd-102">ICorDebugChain::GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="18cdd-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="18cdd-103">このチェーンを呼び出したチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="18cdd-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18cdd-104">構文</span><span class="sxs-lookup"><span data-stu-id="18cdd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18cdd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18cdd-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="18cdd-106">入出力呼び出し元チェーンを表す、のオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18cdd-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="18cdd-107">(このチェーンまたはデバッガーが呼び出し履歴を初期化した場合のように) このチェーンが自発的`ppChain`に呼び出された場合、は null になります。</span><span class="sxs-lookup"><span data-stu-id="18cdd-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18cdd-108">解説</span><span class="sxs-lookup"><span data-stu-id="18cdd-108">Remarks</span></span>  
 <span data-ttu-id="18cdd-109">呼び出しがスレッド間でマーシャリングされている場合は、呼び出し元のチェーンが別のスレッドに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18cdd-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18cdd-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="18cdd-110">Requirements</span></span>  
 <span data-ttu-id="18cdd-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18cdd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18cdd-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18cdd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18cdd-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18cdd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18cdd-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18cdd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
