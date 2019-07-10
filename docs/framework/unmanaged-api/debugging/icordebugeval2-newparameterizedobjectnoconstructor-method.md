---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4434f5d0eaa45c9cfcbadb20b29564f0643a2dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754436"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="8b90e-102">ICorDebugEval2::NewParameterizedObjectNoConstructor メソッド</span><span class="sxs-lookup"><span data-stu-id="8b90e-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="8b90e-103">コンス トラクター メソッドを呼び出さずに、指定したクラスの新しい型のパラメーター化されたオブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="8b90e-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b90e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b90e-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b90e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b90e-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="8b90e-106">[in]ICorDebugClass を表すオブジェクトをインスタンス化されるオブジェクトのクラスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8b90e-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="8b90e-107">[in]型引数の数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="8b90e-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="8b90e-108">[in]ICorDebugType を表すオブジェクトをインスタンス化されているオブジェクトの型引数が指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="8b90e-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b90e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b90e-109">Remarks</span></span>  
 <span data-ttu-id="8b90e-110">`NewParameterizedObjectNoConstructor`メソッドには、型引数の数が正しくない場合は失敗または間違った型の引数の型が渡されます。</span><span class="sxs-lookup"><span data-stu-id="8b90e-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b90e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b90e-111">Requirements</span></span>  
 <span data-ttu-id="8b90e-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b90e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b90e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b90e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b90e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b90e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b90e-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b90e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
