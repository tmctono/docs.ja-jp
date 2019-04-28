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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645267"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="9d0c8-102">ICorDebugChain::GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="9d0c8-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="9d0c8-103">スレッドの前のフレーム チェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d0c8-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d0c8-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d0c8-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d0c8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d0c8-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="9d0c8-106">[out]このスレッドのフレームの以前のチェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9d0c8-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="9d0c8-107">このチェーンの最初のチェーン場合`ppChain`が null です。</span><span class="sxs-lookup"><span data-stu-id="9d0c8-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d0c8-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9d0c8-108">Requirements</span></span>  
 <span data-ttu-id="9d0c8-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d0c8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d0c8-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d0c8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d0c8-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d0c8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d0c8-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d0c8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
