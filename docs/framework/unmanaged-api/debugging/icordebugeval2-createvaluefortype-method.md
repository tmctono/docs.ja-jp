---
title: ICorDebugEval2::CreateValueForType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: 20315dfc426b63f2d526f3481756e165b388b41e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137606"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="f852b-102">ICorDebugEval2::CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="f852b-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="f852b-103">初期値が0または null の、指定した型の新しい ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f852b-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f852b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f852b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f852b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f852b-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="f852b-106">から型を表す、の型のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f852b-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f852b-107">入出力値を表す `ICorDebugValue` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f852b-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f852b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f852b-108">Remarks</span></span>  
 <span data-ttu-id="f852b-109">`List<int>`などの構築された型を含む任意のオブジェクトの種類を指定できるようにすることで、`CreateValueForType` 一般化の[eval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="f852b-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="f852b-110">このメソッドの唯一の目的は、関数の評価に渡すことができる値を生成することです。</span><span class="sxs-lookup"><span data-stu-id="f852b-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="f852b-111">型はクラスまたは値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f852b-111">The type must be a class or a value type.</span></span> <span data-ttu-id="f852b-112">このメソッドを使用して配列値や文字列値を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f852b-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f852b-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="f852b-113">Requirements</span></span>  
 <span data-ttu-id="f852b-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f852b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f852b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f852b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f852b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f852b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f852b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f852b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
