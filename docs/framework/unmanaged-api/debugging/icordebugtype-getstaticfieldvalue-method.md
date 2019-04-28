---
title: ICorDebugType::GetStaticFieldValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c6b86c5ce3cc246af600d9b65d2fe12a0427f9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663844"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="73cd7-102">ICorDebugType::GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="73cd7-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="73cd7-103">指定したスタック フレームでトークンを指定したフィールドによって参照される静的フィールドの値を含む ICorDebugValue オブジェクトにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="73cd7-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73cd7-104">構文</span><span class="sxs-lookup"><span data-stu-id="73cd7-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73cd7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73cd7-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="73cd7-106">[in]`mdFieldDef`トークンを静的フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="73cd7-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="73cd7-107">[in]スタック フレームを表す、ICorDebugFrame へのポインター。</span><span class="sxs-lookup"><span data-stu-id="73cd7-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="73cd7-108">[out]アドレスへのポインター、`ICorDebugValue`静的フィールドの値を格納します。</span><span class="sxs-lookup"><span data-stu-id="73cd7-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73cd7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="73cd7-109">Remarks</span></span>  
 <span data-ttu-id="73cd7-110">`GetStaticFieldValue`メソッドは使用できます、型が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE 場合に、のみで示されている、 [icordebugtype::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="73cd7-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="73cd7-111">非ジェネリック型の場合、操作を実行して`GetStaticFieldValue`を呼び出すことと同じ[icordebugclass::getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass オブジェクトによって返される[icordebugtype::getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="73cd7-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="73cd7-112">ジェネリック型は、静的フィールドの値は、特定のインスタンス化を基準になります。</span><span class="sxs-lookup"><span data-stu-id="73cd7-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="73cd7-113">また、静的フィールドがスレッド、コンテキスト、またはアプリケーション ドメインを基準とした可能性がある場合は、スタック フレームをデバッガーで適切な値の確認は役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73cd7-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73cd7-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="73cd7-114">Remarks</span></span>  
 <span data-ttu-id="73cd7-115">`GetStaticFieldValue` 呼び出す場合にのみ使用できます`ICorDebugType::GetType`ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の値を返します。</span><span class="sxs-lookup"><span data-stu-id="73cd7-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73cd7-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="73cd7-116">Requirements</span></span>  
 <span data-ttu-id="73cd7-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73cd7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73cd7-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73cd7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73cd7-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73cd7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73cd7-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73cd7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
