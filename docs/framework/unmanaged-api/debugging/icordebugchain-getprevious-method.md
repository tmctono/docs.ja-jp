---
title: ICorDebugChain::GetPrevious メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fdcdf23dfee01e8bad1c95adb4de66f270d5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474970"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="be008-102">ICorDebugChain::GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="be008-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="be008-103">スレッドの前のフレーム チェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="be008-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be008-104">構文</span><span class="sxs-lookup"><span data-stu-id="be008-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be008-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be008-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="be008-106">[out]このスレッドのフレームの以前のチェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="be008-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="be008-107">このチェーンの最初のチェーン場合`ppChain`が null です。</span><span class="sxs-lookup"><span data-stu-id="be008-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be008-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="be008-108">Requirements</span></span>  
 <span data-ttu-id="be008-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be008-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be008-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be008-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be008-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be008-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be008-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be008-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
