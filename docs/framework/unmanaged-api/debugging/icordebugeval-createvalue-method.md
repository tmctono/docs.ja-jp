---
title: ICorDebugEval::CreateValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
ms.openlocfilehash: 55888786fdd8ff2b1d5610a74ee729db0d4fcfde
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976253"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="0cc5c-102">ICorDebugEval::CreateValue メソッド</span><span class="sxs-lookup"><span data-stu-id="0cc5c-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="0cc5c-103">初期値を0または null にして、指定した型の値を作成します。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="0cc5c-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="0cc5c-105">代わりに[ICorDebugEval2:: CreateValueForType](icordebugeval2-createvaluefortype-method.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-105">Use [ICorDebugEval2::CreateValueForType](icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cc5c-106">構文</span><span class="sxs-lookup"><span data-stu-id="0cc5c-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cc5c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0cc5c-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="0cc5c-108">から値の型を指定する[Corelementtype](../metadata/corelementtype-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-108">[in] A value of the [CorElementType](../metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="0cc5c-109">から型がプリミティブ型ではない場合に、値のクラスを指定[する、のオブジェクトへ](icordebugclass-interface.md)のポインター。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-109">[in] Pointer to an [ICorDebugClass](icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0cc5c-110">入出力値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cc5c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="0cc5c-111">Remarks</span></span>  
 <span data-ttu-id="0cc5c-112">`CreateValue`関数の`ICorDebugValue`評価で使用するための唯一の目的で、指定された型のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="0cc5c-113">この値オブジェクトを使用して、ユーザー定数をパラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="0cc5c-114">値の型がプリミティブ型の場合、初期値は0または null になります。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="0cc5c-115">の型の値を設定するには、を[使用します](icordebuggenericvalue-setvalue-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-115">Use [ICorDebugGenericValue::SetValue](icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="0cc5c-116">の`elementType`値が ELEMENT_TYPE_CLASS 場合は、null オブジェクト参照を表す "の値 (で`ppValue`返される) を取得します。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="0cc5c-117">このオブジェクトを使用すると、オブジェクト参照パラメーターを持つ関数の評価に null を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="0cc5c-118">`ICorDebugValue`を何にも設定することはできません。常に null のままです。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cc5c-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="0cc5c-119">Requirements</span></span>  
 <span data-ttu-id="0cc5c-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cc5c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cc5c-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cc5c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cc5c-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cc5c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cc5c-123">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="0cc5c-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc5c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cc5c-124">See also</span></span>

- [<span data-ttu-id="0cc5c-125">CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="0cc5c-125">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="0cc5c-126">ICorDebugEval インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cc5c-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
