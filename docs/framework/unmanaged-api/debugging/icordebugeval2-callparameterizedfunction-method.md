---
title: ICorDebugEval2::CallParameterizedFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: b521c96d26202119dad6fedb61cbd9da8b3c2e52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137638"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="8a701-102">ICorDebugEval2::CallParameterizedFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="8a701-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="8a701-103">指定されたは、パラメーターを <xref:System.Type> 受け取るコンストラクターを持つクラスの内部に入れ子にすることができます。また、パラメーターの <xref:System.Type> を受け取ることもできる、指定されたのに対して、この関数の呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a701-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a701-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a701-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a701-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a701-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="8a701-106">から呼び出される関数を表す `ICorDebugFunction` オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a701-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="8a701-107">から関数が受け取る引数の数。</span><span class="sxs-lookup"><span data-stu-id="8a701-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="8a701-108">からポインターの配列。各ポインターは、関数の引数を表す、テキストオブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="8a701-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="8a701-109">から関数で渡される値の数。</span><span class="sxs-lookup"><span data-stu-id="8a701-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="8a701-110">からポインターの配列。各ポインターは、関数の引数で渡された値を表す ICorDebugValue オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="8a701-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a701-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a701-111">Remarks</span></span>  
 <span data-ttu-id="8a701-112">`CallParameterizedFunction` は、型パラメーターを持つクラス内に存在しても、それ自体が型パラメーターを受け取る可能性があるか、またはその両方であることを除いて、は、のように[します。](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)</span><span class="sxs-lookup"><span data-stu-id="8a701-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="8a701-113">型引数は、クラスに対して最初に指定する必要があります。その後、関数に対して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a701-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="8a701-114">関数が別のアプリケーションドメインにある場合は、遷移が発生します。</span><span class="sxs-lookup"><span data-stu-id="8a701-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="8a701-115">ただし、すべての型引数と値引数は、ターゲットアプリケーションドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a701-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="8a701-116">関数の評価は、限られたシナリオでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a701-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="8a701-117">`CallParameterizedFunction` または `ICorDebugEval::CallFunction` が失敗した場合、返される HRESULT は失敗の最も一般的な原因を示します。</span><span class="sxs-lookup"><span data-stu-id="8a701-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a701-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="8a701-118">Requirements</span></span>  
 <span data-ttu-id="8a701-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a701-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a701-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a701-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a701-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a701-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a701-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a701-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
