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
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791268"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="a2df0-102">ICorDebugType::GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="a2df0-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="a2df0-103">指定したスタックフレーム内の指定したフィールドトークンによって参照される静的フィールドの値を格納する、ICorDebugValue オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a2df0-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2df0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2df0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2df0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2df0-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="a2df0-106">から静的フィールドを指定する `mdFieldDef` トークンです。</span><span class="sxs-lookup"><span data-stu-id="a2df0-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="a2df0-107">からスタックフレームを表す、テキストフレームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2df0-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a2df0-108">入出力静的フィールドの値を格納している `ICorDebugValue` のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2df0-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2df0-109">コメント</span><span class="sxs-lookup"><span data-stu-id="a2df0-109">Remarks</span></span>  
 <span data-ttu-id="a2df0-110">`GetStaticFieldValue` メソッドは、型が ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の場合にのみ使用できます。この場合、は、テキスト[:: GetType](icordebugtype-gettype-method.md)メソッドによって示されます。</span><span class="sxs-lookup"><span data-stu-id="a2df0-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="a2df0-111">非ジェネリック型の場合、`GetStaticFieldValue` によって実行される操作は、によって返される、は、によって返された、テキスト:: [GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)と同じにすることができます、には、[テキスト:: getclass](icordebugtype-getclass-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2df0-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="a2df0-112">ジェネリック型の場合、静的フィールド値は特定のインスタンス化に対して相対的になります。</span><span class="sxs-lookup"><span data-stu-id="a2df0-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="a2df0-113">また、静的フィールドがスレッド、コンテキスト、またはアプリケーションドメインに対して相対的である可能性がある場合は、デバッガーが適切な値を決定するためにスタックフレームが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a2df0-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2df0-114">コメント</span><span class="sxs-lookup"><span data-stu-id="a2df0-114">Remarks</span></span>  
 <span data-ttu-id="a2df0-115">`GetStaticFieldValue` は、`ICorDebugType::GetType` の呼び出しによって ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE の値が返された場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2df0-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2df0-116">要件</span><span class="sxs-lookup"><span data-stu-id="a2df0-116">Requirements</span></span>  
 <span data-ttu-id="a2df0-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2df0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2df0-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2df0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2df0-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2df0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2df0-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2df0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
