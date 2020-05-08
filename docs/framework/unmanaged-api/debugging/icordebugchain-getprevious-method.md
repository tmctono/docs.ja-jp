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
ms.openlocfilehash: a57e73495ac22a25a5f13c06d4c75dee7dde41e0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894630"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="8f837-102">ICorDebugChain::GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="8f837-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="8f837-103">スレッドの前のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f837-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f837-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f837-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f837-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f837-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="8f837-106">入出力このスレッドのフレームの前のチェーンを表す、のオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8f837-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="8f837-107">このチェーンが最初のチェーンの場合`ppChain` 、は null です。</span><span class="sxs-lookup"><span data-stu-id="8f837-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f837-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f837-108">Requirements</span></span>  
 <span data-ttu-id="8f837-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f837-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f837-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f837-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f837-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f837-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f837-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f837-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
