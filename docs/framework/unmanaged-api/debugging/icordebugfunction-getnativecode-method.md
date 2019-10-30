---
title: ICorDebugFunction::GetNativeCode メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 5bb41b2b49922475550997f18832b391522e2f26
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137865"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="cceee-102">ICorDebugFunction::GetNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="cceee-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="cceee-103">このコード例で表される関数のネイティブコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="cceee-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cceee-104">構文</span><span class="sxs-lookup"><span data-stu-id="cceee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cceee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cceee-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="cceee-106">入出力この関数のネイティブコードを表す、のコードインスタンスへのポインター。この関数が just-in-time (JIT) コンパイルされていない Microsoft 中間言語 (MSIL) コードの場合は null。</span><span class="sxs-lookup"><span data-stu-id="cceee-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cceee-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cceee-107">Remarks</span></span>  
 <span data-ttu-id="cceee-108">この `ICorDebugFunction` インスタンスによって表される関数が、ジェネリック型の場合と同じように JIT コンパイルされた場合、`GetNativeCode` はランダムなネイティブコードオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cceee-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cceee-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="cceee-109">Requirements</span></span>  
 <span data-ttu-id="cceee-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cceee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cceee-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cceee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cceee-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cceee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cceee-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cceee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
