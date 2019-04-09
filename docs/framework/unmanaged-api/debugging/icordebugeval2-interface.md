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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3767368c9da8c97cd081787c0945a15552a1da46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092670"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="14ec1-102">ICorDebugEval2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14ec1-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="14ec1-103">「できるように」のジェネリック型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="14ec1-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14ec1-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-104">Methods</span></span>  
  
|<span data-ttu-id="14ec1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-105">Method</span></span>|<span data-ttu-id="14ec1-106">説明</span><span class="sxs-lookup"><span data-stu-id="14ec1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14ec1-107">CallParameterizedFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="14ec1-108">指定された"ICorDebugFunction"、型コンス トラクターが型パラメーターを受け取るまたは型パラメーターを受け取り自体の内部で入れ子にできるへの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="14ec1-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="14ec1-109">CreateValueForType メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="14ec1-110">初期値が null または 0 の指定した型の新しい"ICorDebugValue"へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="14ec1-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="14ec1-111">NewParameterizedArray メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="14ec1-112">指定した要素型とディメンションの新しい配列を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="14ec1-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="14ec1-113">NewParameterizedObject メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="14ec1-114">新しいパラメーター化された型のオブジェクトをインスタンス化して、オブジェクトのコンス トラクター メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="14ec1-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="14ec1-115">NewParameterizedObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="14ec1-116">コンス トラクター メソッドを呼び出さずに、指定したクラスの新しい型のパラメーター化されたオブジェクトをインスタンス化します</span><span class="sxs-lookup"><span data-stu-id="14ec1-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="14ec1-117">NewStringWithLength メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="14ec1-118">指定した内容を指定した長さの新しい文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="14ec1-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="14ec1-119">RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="14ec1-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="14ec1-120">計算の中止この`ICorDebugEval2`は現在実行中です。</span><span class="sxs-lookup"><span data-stu-id="14ec1-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14ec1-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="14ec1-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14ec1-122">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="14ec1-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14ec1-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="14ec1-123">Requirements</span></span>  
 <span data-ttu-id="14ec1-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ec1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14ec1-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14ec1-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14ec1-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14ec1-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="14ec1-127">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="14ec1-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14ec1-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="14ec1-128">See also</span></span>

- [<span data-ttu-id="14ec1-129">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="14ec1-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
