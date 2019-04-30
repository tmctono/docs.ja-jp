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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 156c16f73916d2b4efa1c1b3541a772fb43dd470
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988768"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="70634-102">ICorDebugFrame::GetFunctionToken メソッド</span><span class="sxs-lookup"><span data-stu-id="70634-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="70634-103">このスタック フレームに関連付けられているコードを含む関数のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="70634-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70634-104">構文</span><span class="sxs-lookup"><span data-stu-id="70634-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70634-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70634-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="70634-106">[out]ポインター、`mdMethodDef`関数のメタデータを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="70634-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70634-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="70634-107">Requirements</span></span>  
 <span data-ttu-id="70634-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70634-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70634-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70634-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70634-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70634-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70634-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70634-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
