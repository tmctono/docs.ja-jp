---
title: ICorDebugGenericValue::GetValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: 7923008eecb9011bead685fbbb7f05f81f12329b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138585"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="fc1a9-102">ICorDebugGenericValue::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="fc1a9-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="fc1a9-103">このジェネリックの値を、指定したバッファーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fc1a9-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1a9-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc1a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc1a9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc1a9-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="fc1a9-106">入出力このは、この値オブジェクトによって表される値へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="fc1a9-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="fc1a9-107">値には、単純型または参照型 (つまり、ポインター) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fc1a9-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc1a9-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="fc1a9-108">Requirements</span></span>  
 <span data-ttu-id="fc1a9-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc1a9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc1a9-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc1a9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc1a9-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc1a9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc1a9-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc1a9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
