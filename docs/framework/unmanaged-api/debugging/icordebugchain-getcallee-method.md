---
title: ICorDebugChain::GetCallee メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744986"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="d008f-102">ICorDebugChain::GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="d008f-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="d008f-103">このチェーンによって呼び出されたチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d008f-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d008f-104">構文</span><span class="sxs-lookup"><span data-stu-id="d008f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d008f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d008f-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="d008f-106">[out]呼び出されたチェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d008f-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="d008f-107">場合 (つまり、このチェーンを返すと呼ばれるチェーンが待機していない) 場合、このチェーンは現在実行中、`ppChain`は null になります。</span><span class="sxs-lookup"><span data-stu-id="d008f-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d008f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d008f-108">Remarks</span></span>  
 <span data-ttu-id="d008f-109">このチェーンは、呼び出されたチェーンに戻りますが、実行を再開する前に待機します。</span><span class="sxs-lookup"><span data-stu-id="d008f-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="d008f-110">スレッド間マーシャ リングされた呼び出しの場合、別のスレッドで呼び出されたチェーンがあります。</span><span class="sxs-lookup"><span data-stu-id="d008f-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d008f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d008f-111">Requirements</span></span>  
 <span data-ttu-id="d008f-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d008f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d008f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d008f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d008f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d008f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d008f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d008f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
