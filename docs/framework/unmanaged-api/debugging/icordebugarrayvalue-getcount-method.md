---
title: ICorDebugArrayValue::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d00c04f3719d6fb340541d3301d4dc4a3f95ca40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645722"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="b3ea3-102">ICorDebugArrayValue::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="b3ea3-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="b3ea3-103">配列の要素の合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ea3-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ea3-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3ea3-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3ea3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3ea3-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="b3ea3-106">[out]配列内の要素の総数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b3ea3-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3ea3-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3ea3-107">Requirements</span></span>  
 <span data-ttu-id="b3ea3-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ea3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ea3-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3ea3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3ea3-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3ea3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3ea3-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ea3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
