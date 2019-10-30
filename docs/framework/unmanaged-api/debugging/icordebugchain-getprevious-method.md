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
ms.openlocfilehash: c7598a9d93631ca93187886fd8929ba10726dad7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124729"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="f84c6-102">ICorDebugChain::GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="f84c6-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="f84c6-103">スレッドの前のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f84c6-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f84c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="f84c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f84c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f84c6-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="f84c6-106">入出力このスレッドのフレームの前のチェーンを表す、のオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f84c6-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="f84c6-107">このチェーンが最初のチェーンの場合、`ppChain` は null になります。</span><span class="sxs-lookup"><span data-stu-id="f84c6-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f84c6-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="f84c6-108">Requirements</span></span>  
 <span data-ttu-id="f84c6-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f84c6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f84c6-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f84c6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f84c6-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f84c6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f84c6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f84c6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
