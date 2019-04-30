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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53db4dcb13303c9e7bdd77a46b3c9526364bac06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995646"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="9d7a8-102">ICorDebugGenericValue::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="9d7a8-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="9d7a8-103">このジェネリックの値は、指定されたバッファーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d7a8-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d7a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d7a8-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d7a8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d7a8-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="9d7a8-106">[out]ICorDebugGenericValue オブジェクトによって表される値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9d7a8-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="9d7a8-107">値には、単純型または参照型 (つまり、ポインター) があります。</span><span class="sxs-lookup"><span data-stu-id="9d7a8-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d7a8-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9d7a8-108">Requirements</span></span>  
 <span data-ttu-id="9d7a8-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d7a8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d7a8-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d7a8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d7a8-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d7a8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d7a8-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d7a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
