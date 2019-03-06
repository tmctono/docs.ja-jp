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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 032c1e3dcfe50cd30953ca581ff9f0d83b78518d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488473"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="33cb1-102">ICorDebugFrame::GetChain メソッド</span><span class="sxs-lookup"><span data-stu-id="33cb1-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="33cb1-103">このフレームの一部であるチェーンにポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="33cb1-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="33cb1-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33cb1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="33cb1-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="33cb1-106">[out]このフレームを含むチェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="33cb1-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cb1-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="33cb1-107">Requirements</span></span>  
 <span data-ttu-id="33cb1-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33cb1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33cb1-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33cb1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33cb1-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33cb1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33cb1-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33cb1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
