---
title: ICorDebugFrame::GetChain メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
ms.openlocfilehash: 9677fd14f50cf93eac7eeaef784082d45e8884c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137686"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="f6770-102">ICorDebugFrame::GetChain メソッド</span><span class="sxs-lookup"><span data-stu-id="f6770-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="f6770-103">このフレームが含まれているチェーンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f6770-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6770-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6770-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6770-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6770-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="f6770-106">入出力このフレームを含むチェーンを表す、のオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f6770-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6770-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="f6770-107">Requirements</span></span>  
 <span data-ttu-id="f6770-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6770-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6770-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6770-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6770-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6770-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6770-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6770-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
