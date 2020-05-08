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
ms.openlocfilehash: 98a9b285323bc3ad94b4f555e72a4b3242519801
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976292"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="63f4b-102">ICorDebugEval::Abort メソッド</span><span class="sxs-lookup"><span data-stu-id="63f4b-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="63f4b-103">こののオブジェクトが現在実行している計算を中止します。</span><span class="sxs-lookup"><span data-stu-id="63f4b-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="63f4b-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="63f4b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="63f4b-105">Remarks</span></span>  
 <span data-ttu-id="63f4b-106">評価が入れ子になっていて、それが最新ではない`Abort`場合、メソッドは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63f4b-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f4b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="63f4b-107">Requirements</span></span>  
 <span data-ttu-id="63f4b-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f4b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f4b-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63f4b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63f4b-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63f4b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63f4b-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f4b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
