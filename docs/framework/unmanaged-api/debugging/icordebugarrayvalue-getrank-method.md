---
title: ICorDebugArrayValue::GetRank メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 699c65aae205efd5b08f1d163b4ff9a223bbc217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645657"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="cbd0a-102">ICorDebugArrayValue::GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="cbd0a-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="cbd0a-103">配列のディメンションの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="cbd0a-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd0a-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbd0a-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbd0a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbd0a-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="cbd0a-106">[out]このディメンションの数へのポインター`ICorDebugArrayValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cbd0a-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbd0a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbd0a-107">Requirements</span></span>  
 <span data-ttu-id="cbd0a-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbd0a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd0a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbd0a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbd0a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbd0a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbd0a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd0a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
