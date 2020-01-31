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
ms.openlocfilehash: 8632799b68ae8f92835d1774472bc1432d886f3b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793485"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="a8443-102">ICorDebugEval2::CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="a8443-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="a8443-103">初期値が0または null の、指定した型の新しい ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8443-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8443-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8443-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8443-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8443-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a8443-106">から型を表す、の型のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8443-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a8443-107">入出力値を表す `ICorDebugValue` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a8443-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8443-108">コメント</span><span class="sxs-lookup"><span data-stu-id="a8443-108">Remarks</span></span>  
 <span data-ttu-id="a8443-109">`List<int>`などの構築された型を含む任意のオブジェクトの種類を指定できるようにすることで、`CreateValueForType` 一般化の[eval:: CreateValue](icordebugeval-createvalue-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8443-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="a8443-110">このメソッドの唯一の目的は、関数の評価に渡すことができる値を生成することです。</span><span class="sxs-lookup"><span data-stu-id="a8443-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="a8443-111">型はクラスまたは値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8443-111">The type must be a class or a value type.</span></span> <span data-ttu-id="a8443-112">このメソッドを使用して配列値や文字列値を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8443-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8443-113">要件</span><span class="sxs-lookup"><span data-stu-id="a8443-113">Requirements</span></span>  
 <span data-ttu-id="a8443-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8443-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8443-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8443-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8443-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8443-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8443-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8443-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
