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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645280"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="533c5-102">ICorDebugChain::GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="533c5-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="533c5-103">このチェーンと呼ばれるチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="533c5-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="533c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="533c5-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="533c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="533c5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="533c5-106">[out]呼び出し元のチェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="533c5-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="533c5-107">このチェーンが自発的に呼び出された場合 (このチェーンやデバッガーに呼び出し履歴が初期化されている場合、ケースになります) として、`ppChain`は null になります。</span><span class="sxs-lookup"><span data-stu-id="533c5-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="533c5-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="533c5-108">Remarks</span></span>  
 <span data-ttu-id="533c5-109">呼び出しがスレッド間でマーシャ リングされた場合、別のスレッドで呼び出しチェーンがあります。</span><span class="sxs-lookup"><span data-stu-id="533c5-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="533c5-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="533c5-110">Requirements</span></span>  
 <span data-ttu-id="533c5-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="533c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="533c5-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="533c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="533c5-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="533c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="533c5-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="533c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
