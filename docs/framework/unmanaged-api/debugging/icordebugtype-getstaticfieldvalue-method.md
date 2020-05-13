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
ms.openlocfilehash: 83ac91133b226e2ac263356941c3fc3288355e7e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379933"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="9e3fe-102">ICorDebugType::GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="9e3fe-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="9e3fe-103">指定したスタックフレーム内の指定したフィールドトークンによって参照される静的フィールドの値を格納する、ICorDebugValue オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e3fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e3fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e3fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e3fe-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="9e3fe-106">から`mdFieldDef`静的フィールドを指定するトークンです。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="9e3fe-107">からスタックフレームを表す、テキストフレームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9e3fe-108">入出力`ICorDebugValue`静的フィールドの値を格納しているのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e3fe-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e3fe-109">Remarks</span></span>  
 <span data-ttu-id="9e3fe-110">メソッドが使用されるのは、 `GetStaticFieldValue` 型が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE である場合です。この場合、は、"の[型:: GetType](icordebugtype-gettype-method.md)メソッドによって示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="9e3fe-111">非ジェネリック型の場合、によって実行される操作は、によって返される、によって `GetStaticFieldValue` 型: [: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)を呼び出すことと同じになります。このクラスは、[テキスト:: getclass](icordebugtype-getclass-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="9e3fe-112">ジェネリック型の場合、静的フィールド値は特定のインスタンス化に対して相対的になります。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="9e3fe-113">また、静的フィールドがスレッド、コンテキスト、またはアプリケーションドメインに対して相対的である可能性がある場合は、デバッガーが適切な値を決定するためにスタックフレームが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e3fe-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e3fe-114">Remarks</span></span>  
 <span data-ttu-id="9e3fe-115">`GetStaticFieldValue`は、の呼び出しによって `ICorDebugType::GetType` ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の値が返される場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e3fe-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e3fe-116">Requirements</span></span>  
 <span data-ttu-id="9e3fe-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e3fe-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e3fe-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e3fe-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e3fe-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e3fe-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e3fe-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e3fe-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
