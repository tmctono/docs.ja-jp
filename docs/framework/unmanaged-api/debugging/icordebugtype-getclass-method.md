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
ms.openlocfilehash: 3a895f432ed640cc35a492df0c91cece34893062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122363"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="eaff9-102">ICorDebugType::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="eaff9-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="eaff9-103">インスタンスジェネリック型を表す、のクラスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="eaff9-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaff9-104">構文</span><span class="sxs-lookup"><span data-stu-id="eaff9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaff9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eaff9-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="eaff9-106">入出力インスタンスジェネリック型を表す `ICorDebugClass` インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eaff9-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaff9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="eaff9-107">Remarks</span></span>  
 <span data-ttu-id="eaff9-108">`GetClass` は、特定の条件下でのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="eaff9-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="eaff9-109">`GetClass`を呼び出す前に、を呼び出し[てください。](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)</span><span class="sxs-lookup"><span data-stu-id="eaff9-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="eaff9-110">`ICorDebugType::GetType` が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の CorElementType 値を返す場合、`GetClass` を呼び出して、ジェネリック型のインスタンス型を取得できます。</span><span class="sxs-lookup"><span data-stu-id="eaff9-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaff9-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="eaff9-111">Requirements</span></span>  
 <span data-ttu-id="eaff9-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaff9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaff9-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eaff9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaff9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaff9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaff9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaff9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
