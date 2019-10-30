---
title: ICorDebugFrame::GetFunctionToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
ms.openlocfilehash: e7821022e6966dbdea90d57b6899f09b2ed1964e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090521"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="488c4-102">ICorDebugFrame::GetFunctionToken メソッド</span><span class="sxs-lookup"><span data-stu-id="488c4-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="488c4-103">このスタックフレームに関連付けられているコードを含む関数のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="488c4-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="488c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="488c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="488c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="488c4-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="488c4-106">入出力関数のメタデータを参照する `mdMethodDef` トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="488c4-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="488c4-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="488c4-107">Requirements</span></span>  
 <span data-ttu-id="488c4-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="488c4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="488c4-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="488c4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="488c4-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="488c4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="488c4-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="488c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
