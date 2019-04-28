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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c16f6d1334888fc389a7c39cf0a3865afca2085
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934746"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="f1fdc-102">ICorDebugEval::CreateValue メソッド</span><span class="sxs-lookup"><span data-stu-id="f1fdc-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="f1fdc-103">0 または null の初期値を持つ指定した型の値を作成します。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="f1fdc-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f1fdc-105">使用[icordebugeval 2::createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fdc-106">構文</span><span class="sxs-lookup"><span data-stu-id="f1fdc-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1fdc-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1fdc-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="f1fdc-108">[in]値、 [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md)列挙値の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="f1fdc-109">[in]ポインター、 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)型がプリミティブ型でない場合、値のクラスを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f1fdc-110">[out]値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1fdc-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1fdc-111">Remarks</span></span>  
 <span data-ttu-id="f1fdc-112">`CreateValue` 作成、`ICorDebugValue`の関数の評価で使用する目的で指定された型のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="f1fdc-113">この値オブジェクトは、ユーザーの定数をパラメーターとして渡すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="f1fdc-114">その初期値は 0 で、値の型がプリミティブ型の場合は null です。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="f1fdc-115">使用[icordebuggenericvalue::setvalue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)プリミティブ型の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="f1fdc-116">場合の値`elementType`ELEMENT_TYPE_CLASS は、"ICorDebugReferenceValue"を取得する (で返される`ppValue`) null オブジェクト参照を表します。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="f1fdc-117">このオブジェクトを使用して、オブジェクト参照のパラメーターを持つ関数の評価に null を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="f1fdc-118">設定することはできません、`ICorDebugValue`に何も常に null です。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1fdc-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1fdc-119">Requirements</span></span>  
 <span data-ttu-id="f1fdc-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1fdc-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1fdc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1fdc-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1fdc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1fdc-123">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f1fdc-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1fdc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1fdc-124">See also</span></span>

- [<span data-ttu-id="f1fdc-125">CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="f1fdc-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="f1fdc-126">ICorDebugEval インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1fdc-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
