---
title: ICorDebugEval::Abort メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 052c467f5570119cd08b4719c768d178dd52aba2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752210"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="fec5a-102">ICorDebugEval::Abort メソッド</span><span class="sxs-lookup"><span data-stu-id="fec5a-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="fec5a-103">この ICorDebugEval オブジェクトが現在実行して、計算を中止します。</span><span class="sxs-lookup"><span data-stu-id="fec5a-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="fec5a-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fec5a-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="fec5a-105">Remarks</span></span>  
 <span data-ttu-id="fec5a-106">評価が入れ子になっており、最新のものでない場合、`Abort`メソッドが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fec5a-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fec5a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="fec5a-107">Requirements</span></span>  
 <span data-ttu-id="fec5a-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec5a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fec5a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fec5a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fec5a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fec5a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fec5a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fec5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
