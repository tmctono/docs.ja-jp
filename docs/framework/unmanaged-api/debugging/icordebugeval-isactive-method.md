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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d992ea86b3221af222bb01f1985fe277cea5a2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988992"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="8cac7-102">ICorDebugEval::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="8cac7-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="8cac7-103">この ICorDebugEval オブジェクトが現在実行されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8cac7-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cac7-104">構文</span><span class="sxs-lookup"><span data-stu-id="8cac7-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cac7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8cac7-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="8cac7-106">[out]この評価版がアクティブかどうかを示す値を指すポインター。</span><span class="sxs-lookup"><span data-stu-id="8cac7-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cac7-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="8cac7-107">Requirements</span></span>  
 <span data-ttu-id="8cac7-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cac7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cac7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cac7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cac7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cac7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cac7-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cac7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
