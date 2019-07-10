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
ms.openlocfilehash: 1054c7c977a487bb5a4bbf464322a65bcc039608
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755733"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="b9418-102">ICorDebugType::GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="b9418-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="b9418-103">指定したスタック フレームでトークンを指定したフィールドによって参照される静的フィールドの値を含む ICorDebugValue オブジェクトにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b9418-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9418-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9418-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9418-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9418-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="b9418-106">[in]`mdFieldDef`トークンを静的フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9418-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="b9418-107">[in]スタック フレームを表す、ICorDebugFrame へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9418-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b9418-108">[out]アドレスへのポインター、`ICorDebugValue`静的フィールドの値を格納します。</span><span class="sxs-lookup"><span data-stu-id="b9418-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9418-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9418-109">Remarks</span></span>  
 <span data-ttu-id="b9418-110">`GetStaticFieldValue`メソッドは使用できます、型が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE 場合に、のみで示されている、 [icordebugtype::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="b9418-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="b9418-111">非ジェネリック型の場合、操作を実行して`GetStaticFieldValue`を呼び出すことと同じ[icordebugclass::getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass オブジェクトによって返される[icordebugtype::getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="b9418-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="b9418-112">ジェネリック型は、静的フィールドの値は、特定のインスタンス化を基準になります。</span><span class="sxs-lookup"><span data-stu-id="b9418-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="b9418-113">また、静的フィールドがスレッド、コンテキスト、またはアプリケーション ドメインを基準とした可能性がある場合は、スタック フレームをデバッガーで適切な値の確認は役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9418-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9418-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9418-114">Remarks</span></span>  
 <span data-ttu-id="b9418-115">`GetStaticFieldValue` 呼び出す場合にのみ使用できます`ICorDebugType::GetType`ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の値を返します。</span><span class="sxs-lookup"><span data-stu-id="b9418-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9418-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9418-116">Requirements</span></span>  
 <span data-ttu-id="b9418-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9418-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9418-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9418-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9418-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9418-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9418-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9418-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
