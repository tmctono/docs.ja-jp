---
title: ICorDebugGenericValue::SetValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6907cdf78fc70c75ddd711cd8593427857b172
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756894"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="1d420-102">ICorDebugGenericValue::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="1d420-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="1d420-103">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="1d420-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d420-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d420-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d420-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1d420-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="1d420-106">[in]値をコピー元のバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1d420-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d420-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1d420-107">Remarks</span></span>  
 <span data-ttu-id="1d420-108">参照型では、値は、参照、コンテンツではなくです。</span><span class="sxs-lookup"><span data-stu-id="1d420-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d420-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1d420-109">Requirements</span></span>  
 <span data-ttu-id="1d420-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d420-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d420-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d420-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d420-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d420-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d420-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d420-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
