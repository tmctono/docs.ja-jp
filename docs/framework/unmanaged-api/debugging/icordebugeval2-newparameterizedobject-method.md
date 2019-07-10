---
title: ICorDebugEval2::NewParameterizedObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aae5f4c79acd6f92d42c2890ba64fa66e1b4bfbe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753594"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="13c69-102">ICorDebugEval2::NewParameterizedObject メソッド</span><span class="sxs-lookup"><span data-stu-id="13c69-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="13c69-103">新しいパラメーター化された型のオブジェクトをインスタンス化して、オブジェクトのコンス トラクター メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="13c69-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c69-104">構文</span><span class="sxs-lookup"><span data-stu-id="13c69-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13c69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13c69-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="13c69-106">[in]ICorDebugFunction を表すオブジェクトをインスタンス化されるオブジェクトのコンス トラクターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="13c69-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="13c69-107">[in]型引数の数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="13c69-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="13c69-108">[in]ICorDebugType を表すオブジェクトをインスタンス化されているオブジェクトの型引数が指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="13c69-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="13c69-109">[in]コンス トラクターに渡された引数の数。</span><span class="sxs-lookup"><span data-stu-id="13c69-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="13c69-110">[in]コンス トラクターに渡される引数の値を表す ICorDebugValue オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="13c69-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13c69-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="13c69-111">Remarks</span></span>  
 <span data-ttu-id="13c69-112">オブジェクトのコンス トラクターがかかる場合があります<xref:System.Type>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="13c69-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c69-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="13c69-113">Requirements</span></span>  
 <span data-ttu-id="13c69-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13c69-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c69-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13c69-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13c69-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13c69-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13c69-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c69-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
