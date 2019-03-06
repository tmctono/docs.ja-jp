---
title: ICorDebugChain::GetActiveFrame メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14b48a29993a65a0a0ab9fcb63bcb1e0d882042
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494072"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="b5318-102">ICorDebugChain::GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="b5318-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="b5318-103">アクティブなを取得します (つまり、最新) チェーン上のフレーム。</span><span class="sxs-lookup"><span data-stu-id="b5318-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5318-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5318-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5318-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5318-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="b5318-106">[out]アクティブなを表す ICorDebugFrame オブジェクトのアドレスへのポインター (つまり、最新) チェーン上のフレーム。</span><span class="sxs-lookup"><span data-stu-id="b5318-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5318-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5318-107">Remarks</span></span>  
 <span data-ttu-id="b5318-108">マネージ スタック フレームが使用できない場合`ppFrame`設定を null にします。</span><span class="sxs-lookup"><span data-stu-id="b5318-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="b5318-109">アクティブなフレームを使用できない場合、呼び出しが成功し、`ppFrame`は null になります。</span><span class="sxs-lookup"><span data-stu-id="b5318-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="b5318-110">アクティブなフレーム チェーン CHAIN_ENTER_UNMANAGED、により開始されると CHAIN_CLASS_INIT により開始されたいくつかのチェーンで利用できるされません。</span><span class="sxs-lookup"><span data-stu-id="b5318-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="b5318-111">CorDebugChainReason 列挙型を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5318-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5318-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="b5318-112">Requirements</span></span>  
 <span data-ttu-id="b5318-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5318-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5318-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5318-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5318-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5318-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5318-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5318-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
