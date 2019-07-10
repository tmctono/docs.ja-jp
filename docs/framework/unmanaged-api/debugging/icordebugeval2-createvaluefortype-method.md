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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ffddb8242b6627239a99bd9223b98762910b831
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753236"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="47d86-102">ICorDebugEval2::CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="47d86-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="47d86-103">0 または null の初期値を持つ指定した型の新しい ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="47d86-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d86-104">構文</span><span class="sxs-lookup"><span data-stu-id="47d86-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47d86-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47d86-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="47d86-106">[in]型を表す ICorDebugType オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="47d86-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="47d86-107">[out]アドレスへのポインター、`ICorDebugValue`値を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47d86-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d86-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="47d86-108">Remarks</span></span>  
 <span data-ttu-id="47d86-109">`CreateValueForType` 一般化[icordebugeval::createvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)任意のオブジェクトの種類を指定できるためなど構築型など`List<int>`します。</span><span class="sxs-lookup"><span data-stu-id="47d86-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="47d86-110">このメソッドの唯一の目的では、関数の評価に渡すことができる値を生成します。</span><span class="sxs-lookup"><span data-stu-id="47d86-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="47d86-111">種類は、クラスまたは値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47d86-111">The type must be a class or a value type.</span></span> <span data-ttu-id="47d86-112">このメソッドを使用して、配列の値または文字列値を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="47d86-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47d86-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="47d86-113">Requirements</span></span>  
 <span data-ttu-id="47d86-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47d86-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d86-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47d86-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47d86-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47d86-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47d86-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47d86-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
