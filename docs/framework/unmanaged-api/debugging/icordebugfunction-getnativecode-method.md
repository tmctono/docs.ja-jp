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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754600"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="ef68e-102">ICorDebugFunction::GetNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="ef68e-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="ef68e-103">この ICorDebugFunction インスタンスで表される関数のネイティブ コードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ef68e-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef68e-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef68e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef68e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef68e-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="ef68e-106">[out]この関数は、Microsoft intermediate language (MSIL) コードの just-in-time (JIT) コンパイルされていない場合は、この関数の場合、または null の場合、ネイティブ コードを表す ICorDebugCode インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ef68e-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef68e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef68e-107">Remarks</span></span>  
 <span data-ttu-id="ef68e-108">場合、これによって表される関数`ICorDebugFunction`インスタンス JIT でコンパイルされた複数回、ジェネリック型の場合、`GetNativeCode`ランダムなネイティブ コードのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ef68e-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef68e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ef68e-109">Requirements</span></span>  
 <span data-ttu-id="ef68e-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef68e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef68e-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef68e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef68e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef68e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef68e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef68e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
