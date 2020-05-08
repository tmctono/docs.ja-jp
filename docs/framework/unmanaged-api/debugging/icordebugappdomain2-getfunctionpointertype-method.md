---
title: ICorDebugAppDomain2::GetFunctionPointerType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: fb9b5ee329b41a8b842b94d59bd61c8bcf5f0bf5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895148"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="43a49-102">ICorDebugAppDomain2::GetFunctionPointerType メソッド</span><span class="sxs-lookup"><span data-stu-id="43a49-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="43a49-103">指定されたシグネチャを持つ関数へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="43a49-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a49-104">構文</span><span class="sxs-lookup"><span data-stu-id="43a49-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43a49-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43a49-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="43a49-106">から関数の型引数の数。</span><span class="sxs-lookup"><span data-stu-id="43a49-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="43a49-107">からポインターの配列。各ポインターは、関数の型引数を表す、テキスト型のオブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="43a49-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="43a49-108">最初の要素は戻り値の型です。その他の要素はそれぞれパラメーター型です。</span><span class="sxs-lookup"><span data-stu-id="43a49-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="43a49-109">入出力関数へのポインターを表す`ICorDebugType`オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="43a49-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a49-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="43a49-110">Requirements</span></span>  
 <span data-ttu-id="43a49-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a49-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a49-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43a49-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43a49-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43a49-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a49-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a49-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
