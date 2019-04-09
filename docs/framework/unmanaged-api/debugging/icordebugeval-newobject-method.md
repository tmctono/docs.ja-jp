---
title: ICorDebugEval::NewObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c2d6a66eca080b480b508afea36c33b3e0aeec0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178231"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="3e166-102">ICorDebugEval::NewObject メソッド</span><span class="sxs-lookup"><span data-stu-id="3e166-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="3e166-103">オブジェクトの新しいインスタンスの割り当てし、指定したコンス トラクター メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3e166-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="3e166-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="3e166-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3e166-105">使用[icordebugeval 2::newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)代わりにします。</span><span class="sxs-lookup"><span data-stu-id="3e166-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e166-106">構文</span><span class="sxs-lookup"><span data-stu-id="3e166-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e166-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e166-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="3e166-108">[in]呼び出されるコンス トラクターです。</span><span class="sxs-lookup"><span data-stu-id="3e166-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="3e166-109">[in] `ppArgs` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="3e166-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="3e166-110">[in]ICorDebugValue のオブジェクトのコンス トラクターに渡される引数を表す配列。</span><span class="sxs-lookup"><span data-stu-id="3e166-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e166-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e166-111">Requirements</span></span>  
 <span data-ttu-id="3e166-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e166-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e166-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e166-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e166-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e166-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e166-115">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="3e166-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e166-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e166-116">See also</span></span>

- [<span data-ttu-id="3e166-117">NewParameterizedObject メソッド</span><span class="sxs-lookup"><span data-stu-id="3e166-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
