---
title: ICorDebugValue2::GetExactType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 6c5e5d1c9f734e097fc9e871d7a0cffdc9bb9138
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791123"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="819a0-102">ICorDebugValue2::GetExactType メソッド</span><span class="sxs-lookup"><span data-stu-id="819a0-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="819a0-103">この値の <xref:System.Type> を表す "の型のオブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="819a0-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="819a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="819a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="819a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="819a0-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="819a0-106">入出力この "ICorDebugValue2" オブジェクトによって表される値の <xref:System.Type> を表す `ICorDebugType` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="819a0-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="819a0-107">コメント</span><span class="sxs-lookup"><span data-stu-id="819a0-107">Remarks</span></span>  
 <span data-ttu-id="819a0-108">ジェネリック対応の `GetExactType` メソッドは、、の各メソッドと、値の型に関する情報を返す、それぞれのメソッドと[ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) [メソッドの両方](icordebugobjectvalue-getclass-method.md)を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="819a0-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="819a0-109">要件</span><span class="sxs-lookup"><span data-stu-id="819a0-109">Requirements</span></span>  
 <span data-ttu-id="819a0-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="819a0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="819a0-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="819a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="819a0-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="819a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="819a0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="819a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="819a0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="819a0-114">See also</span></span>
