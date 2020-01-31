---
title: ICorDebugObjectValue::GetClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: d15938e94d647fd5fded23c72bdc200d198d21a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792706"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="8c9e1-102">ICorDebugObjectValue::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="8c9e1-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="8c9e1-103">このオブジェクト値のクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c9e1-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c9e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c9e1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c9e1-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="8c9e1-106">入出力この "いい Objectvalue" オブジェクトによって表されるオブジェクト値のクラスを表す "のクラス" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8c9e1-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c9e1-107">コメント</span><span class="sxs-lookup"><span data-stu-id="8c9e1-107">Remarks</span></span>  
 <span data-ttu-id="8c9e1-108">`GetClass` および[ICorDebugValue:: GetType](icordebugvalue-gettype-method.md)メソッドはそれぞれ、値の型に関する情報を返します。これらはどちらも、ジェネリック対応[ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md)に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="8c9e1-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c9e1-109">要件</span><span class="sxs-lookup"><span data-stu-id="8c9e1-109">Requirements</span></span>  
 <span data-ttu-id="8c9e1-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c9e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c9e1-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c9e1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c9e1-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c9e1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c9e1-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c9e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9e1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c9e1-114">See also</span></span>
