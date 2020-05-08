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
ms.openlocfilehash: e9570d3c916123093f69e7f26d3778f1c7184b1f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976188"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="8c680-102">ICorDebugEval::NewObject メソッド</span><span class="sxs-lookup"><span data-stu-id="8c680-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="8c680-103">新しいオブジェクトインスタンスを割り当て、指定したコンストラクターメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c680-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="8c680-104">このメソッドは .NET Framework バージョン2.0 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="8c680-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="8c680-105">代わりに[ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8c680-105">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c680-106">構文</span><span class="sxs-lookup"><span data-stu-id="8c680-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c680-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c680-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="8c680-108">から呼び出されるコンストラクター。</span><span class="sxs-lookup"><span data-stu-id="8c680-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="8c680-109">[in] `ppArgs` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="8c680-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="8c680-110">からICorDebugValue オブジェクトの配列。各オブジェクトは、コンストラクターに渡される引数を表します。</span><span class="sxs-lookup"><span data-stu-id="8c680-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c680-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c680-111">Requirements</span></span>  
 <span data-ttu-id="8c680-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c680-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c680-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c680-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c680-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c680-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c680-115">**.NET Framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="8c680-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c680-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c680-116">See also</span></span>

- [<span data-ttu-id="8c680-117">NewParameterizedObject メソッド</span><span class="sxs-lookup"><span data-stu-id="8c680-117">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
