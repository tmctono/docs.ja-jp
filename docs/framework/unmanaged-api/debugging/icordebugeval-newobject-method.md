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
ms.openlocfilehash: 38cc98f1bfd966d1f764e43b30003a2bae66297d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793467"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="477d2-102">ICorDebugEval::NewObject メソッド</span><span class="sxs-lookup"><span data-stu-id="477d2-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="477d2-103">新しいオブジェクトインスタンスを割り当て、指定したコンストラクターメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="477d2-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="477d2-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="477d2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="477d2-105">代わりに[ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="477d2-105">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="477d2-106">構文</span><span class="sxs-lookup"><span data-stu-id="477d2-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="477d2-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="477d2-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="477d2-108">から呼び出されるコンストラクター。</span><span class="sxs-lookup"><span data-stu-id="477d2-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="477d2-109">[in] `ppArgs` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="477d2-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="477d2-110">からICorDebugValue オブジェクトの配列。各オブジェクトは、コンストラクターに渡される引数を表します。</span><span class="sxs-lookup"><span data-stu-id="477d2-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="477d2-111">要件</span><span class="sxs-lookup"><span data-stu-id="477d2-111">Requirements</span></span>  
 <span data-ttu-id="477d2-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="477d2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="477d2-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="477d2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="477d2-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="477d2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="477d2-115">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="477d2-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477d2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="477d2-116">See also</span></span>

- [<span data-ttu-id="477d2-117">NewParameterizedObject メソッド</span><span class="sxs-lookup"><span data-stu-id="477d2-117">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
