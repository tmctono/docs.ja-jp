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
ms.openlocfilehash: 4cd03895b4e33c3e42c71acca12eaf950fc9a145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138559"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="8424f-102">ICorDebugGenericValue::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="8424f-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="8424f-103">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8424f-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8424f-104">構文</span><span class="sxs-lookup"><span data-stu-id="8424f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8424f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8424f-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="8424f-106">から値のコピー元のバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8424f-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8424f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8424f-107">Remarks</span></span>  
 <span data-ttu-id="8424f-108">参照型の場合、値は参照であり、コンテンツではありません。</span><span class="sxs-lookup"><span data-stu-id="8424f-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8424f-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="8424f-109">Requirements</span></span>  
 <span data-ttu-id="8424f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8424f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8424f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8424f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8424f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8424f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8424f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8424f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
