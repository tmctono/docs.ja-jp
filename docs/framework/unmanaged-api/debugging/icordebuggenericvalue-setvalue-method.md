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
ms.openlocfilehash: ae64fcccb49123f34cca2622a972a89bf700904f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476686"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="8749c-102">ICorDebugGenericValue::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="8749c-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="8749c-103">指定したバッファーから新しい値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8749c-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8749c-104">構文</span><span class="sxs-lookup"><span data-stu-id="8749c-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8749c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8749c-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="8749c-106">[in]値をコピー元のバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8749c-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8749c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8749c-107">Remarks</span></span>  
 <span data-ttu-id="8749c-108">参照型では、値は、参照、コンテンツではなくです。</span><span class="sxs-lookup"><span data-stu-id="8749c-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8749c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8749c-109">Requirements</span></span>  
 <span data-ttu-id="8749c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8749c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8749c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8749c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8749c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8749c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8749c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8749c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
