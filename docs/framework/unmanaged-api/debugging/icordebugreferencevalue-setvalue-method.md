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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804aa4a6508713b2d6f2d154fc47e09638994468
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747365"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="acbd2-102">ICorDebugReferenceValue::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="acbd2-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="acbd2-103">指定されたメモリ アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="acbd2-103">Sets the specified memory address.</span></span> <span data-ttu-id="acbd2-104">つまり、このメソッドは、オブジェクトを指すためにこの ICorDebugReferenceValue を設定します。</span><span class="sxs-lookup"><span data-stu-id="acbd2-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acbd2-105">構文</span><span class="sxs-lookup"><span data-stu-id="acbd2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acbd2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acbd2-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="acbd2-107">[in]A`CORDB_ADDRESS`このオブジェクトのアドレスを指定する値`ICorDebugReferenceValue`ポイント。</span><span class="sxs-lookup"><span data-stu-id="acbd2-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acbd2-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="acbd2-108">Requirements</span></span>  
 <span data-ttu-id="acbd2-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbd2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acbd2-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acbd2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acbd2-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acbd2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acbd2-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acbd2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
