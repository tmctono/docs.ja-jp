---
title: ICorDebugEval2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: b597d95b5b25e5ebf04fac48e4f3fda312a9594c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976123"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="c0f54-102">ICorDebugEval2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0f54-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="c0f54-103">"" は、"" "のように拡張して、ジェネリック型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0f54-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0f54-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-104">Methods</span></span>  
  
|<span data-ttu-id="c0f54-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-105">Method</span></span>|<span data-ttu-id="c0f54-106">説明</span><span class="sxs-lookup"><span data-stu-id="c0f54-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0f54-107">CallParameterizedFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="c0f54-108">指定された "" の呼び出しを設定します。この関数は、コンストラクターが型パラメーターを受け取る型の内部に入れ子にすることも、型パラメーターを受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="c0f54-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="c0f54-109">CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="c0f54-110">初期値が null または0の、指定した型の新しい "ICorDebugValue" へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c0f54-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="c0f54-111">NewParameterizedArray メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="c0f54-112">指定した要素の型と次元の新しい配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c0f54-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="c0f54-113">NewParameterizedObject メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="c0f54-114">新しいパラメーター化された型オブジェクトをインスタンス化し、オブジェクトのコンストラクターメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c0f54-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="c0f54-115">NewParameterizedObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="c0f54-116">コンストラクターメソッドを呼び出さずに、指定したクラスの新しいパラメーター化された型オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="c0f54-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="c0f54-117">NewStringWithLength メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="c0f54-118">指定したコンテンツを使用して、指定した長さの新しい文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0f54-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="c0f54-119">RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="c0f54-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="c0f54-120">この`ICorDebugEval2`が現在実行している計算を中止します。</span><span class="sxs-lookup"><span data-stu-id="c0f54-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f54-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0f54-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0f54-122">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c0f54-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f54-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0f54-123">Requirements</span></span>  
 <span data-ttu-id="c0f54-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f54-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f54-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0f54-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0f54-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0f54-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0f54-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0f54-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f54-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0f54-128">See also</span></span>

- [<span data-ttu-id="c0f54-129">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0f54-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
