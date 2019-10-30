---
title: ICorDebugEval::IsActive メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: bd10af53d7803964ed6e699ce5328aa8a860216c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085018"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="431c6-102">ICorDebugEval::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="431c6-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="431c6-103">この、このオブジェクトが現在実行されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="431c6-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="431c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="431c6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="431c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="431c6-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="431c6-106">入出力この評価がアクティブかどうかを示す値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="431c6-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="431c6-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="431c6-107">Requirements</span></span>  
 <span data-ttu-id="431c6-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="431c6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="431c6-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="431c6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="431c6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="431c6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="431c6-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="431c6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
