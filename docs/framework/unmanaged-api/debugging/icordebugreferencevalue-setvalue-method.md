---
title: ICorDebugReferenceValue::SetValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 61563488bff682cc7a417296c3db8eb7e7cf965a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139317"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="7612b-102">ICorDebugReferenceValue::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="7612b-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="7612b-103">指定されたメモリアドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="7612b-103">Sets the specified memory address.</span></span> <span data-ttu-id="7612b-104">つまり、このメソッドは、オブジェクトを指すようにこの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7612b-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7612b-105">構文</span><span class="sxs-lookup"><span data-stu-id="7612b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7612b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7612b-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="7612b-107">からこの `ICorDebugReferenceValue` が指すオブジェクトのアドレスを指定する `CORDB_ADDRESS` 値。</span><span class="sxs-lookup"><span data-stu-id="7612b-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7612b-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="7612b-108">Requirements</span></span>  
 <span data-ttu-id="7612b-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7612b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7612b-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7612b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7612b-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7612b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7612b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7612b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
