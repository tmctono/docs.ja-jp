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
ms.openlocfilehash: ed5a7657affde335acf79952d77bbdb7ac42c7a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645299"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="30f39-102">ICorDebugChain::GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="30f39-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="30f39-103">このチェーンによって呼び出されたチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="30f39-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f39-104">構文</span><span class="sxs-lookup"><span data-stu-id="30f39-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30f39-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30f39-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="30f39-106">[out]呼び出されたチェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="30f39-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="30f39-107">場合 (つまり、このチェーンを返すと呼ばれるチェーンが待機していない) 場合、このチェーンは現在実行中、`ppChain`は null になります。</span><span class="sxs-lookup"><span data-stu-id="30f39-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30f39-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="30f39-108">Remarks</span></span>  
 <span data-ttu-id="30f39-109">このチェーンは、呼び出されたチェーンに戻りますが、実行を再開する前に待機します。</span><span class="sxs-lookup"><span data-stu-id="30f39-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="30f39-110">スレッド間マーシャ リングされた呼び出しの場合、別のスレッドで呼び出されたチェーンがあります。</span><span class="sxs-lookup"><span data-stu-id="30f39-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f39-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="30f39-111">Requirements</span></span>  
 <span data-ttu-id="30f39-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30f39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f39-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30f39-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30f39-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30f39-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30f39-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f39-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
