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
ms.openlocfilehash: 972a981188c36236b81f3da17c09abeeb1e32857
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212192"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="9feba-102">ICorDebugGenericValue::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="9feba-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="9feba-103">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9feba-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9feba-104">構文</span><span class="sxs-lookup"><span data-stu-id="9feba-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9feba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9feba-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="9feba-106">から値のコピー元のバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9feba-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9feba-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9feba-107">Remarks</span></span>  
 <span data-ttu-id="9feba-108">参照型の場合、値は参照であり、コンテンツではありません。</span><span class="sxs-lookup"><span data-stu-id="9feba-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9feba-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9feba-109">Requirements</span></span>  
 <span data-ttu-id="9feba-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9feba-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9feba-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9feba-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9feba-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9feba-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9feba-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9feba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
