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
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791293"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="586ec-102">ICorDebugType::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="586ec-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="586ec-103">インスタンスジェネリック型を表す、のクラスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="586ec-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="586ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="586ec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="586ec-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="586ec-106">入出力インスタンスジェネリック型を表す `ICorDebugClass` インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="586ec-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="586ec-107">コメント</span><span class="sxs-lookup"><span data-stu-id="586ec-107">Remarks</span></span>  
 <span data-ttu-id="586ec-108">`GetClass` は、特定の条件下でのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="586ec-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="586ec-109">`GetClass`を呼び出す前に、を呼び出し[てください。](icordebugtype-gettype-method.md)</span><span class="sxs-lookup"><span data-stu-id="586ec-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="586ec-110">`ICorDebugType::GetType` が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の CorElementType 値を返す場合、`GetClass` を呼び出して、ジェネリック型のインスタンス型を取得できます。</span><span class="sxs-lookup"><span data-stu-id="586ec-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="586ec-111">要件</span><span class="sxs-lookup"><span data-stu-id="586ec-111">Requirements</span></span>  
 <span data-ttu-id="586ec-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="586ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="586ec-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="586ec-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="586ec-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="586ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="586ec-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="586ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
