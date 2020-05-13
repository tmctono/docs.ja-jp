---
title: ICorDebugType::GetClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379959"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="d7619-102">ICorDebugType::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="d7619-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="d7619-103">インスタンスジェネリック型を表す、のクラスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d7619-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7619-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7619-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7619-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7619-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="d7619-106">入出力`ICorDebugClass`インスタンスジェネリック型を表すインターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d7619-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7619-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7619-107">Remarks</span></span>  
 <span data-ttu-id="d7619-108">`GetClass`は、特定の条件下でのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d7619-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="d7619-109">を[呼び出す前に](icordebugtype-gettype-method.md)、を呼び出して `GetClass` ください。</span><span class="sxs-lookup"><span data-stu-id="d7619-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="d7619-110">`ICorDebugType::GetType`が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の CorElementType 値を返す場合は、を呼び出して、 `GetClass` ジェネリック型のインスタンス型を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d7619-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7619-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7619-111">Requirements</span></span>  
 <span data-ttu-id="d7619-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7619-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7619-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7619-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7619-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7619-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7619-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7619-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
