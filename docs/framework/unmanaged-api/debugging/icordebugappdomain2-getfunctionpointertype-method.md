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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec1a9968dbec10783c6f1383fb523e95ff79561e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683906"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="90a4f-102">ICorDebugAppDomain2::GetFunctionPointerType メソッド</span><span class="sxs-lookup"><span data-stu-id="90a4f-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="90a4f-103">指定されたシグネチャを持つ関数へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="90a4f-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a4f-104">構文</span><span class="sxs-lookup"><span data-stu-id="90a4f-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90a4f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90a4f-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="90a4f-106">[in]関数の型引数の数。</span><span class="sxs-lookup"><span data-stu-id="90a4f-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="90a4f-107">[in]関数の引数の型を表す ICorDebugType オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="90a4f-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="90a4f-108">最初の要素は、戻り値の型です。これらの他の要素は、パラメーターの型です。</span><span class="sxs-lookup"><span data-stu-id="90a4f-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="90a4f-109">[out]アドレスへのポインター、`ICorDebugType`関数へのポインターを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90a4f-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a4f-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="90a4f-110">Requirements</span></span>  
 <span data-ttu-id="90a4f-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90a4f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90a4f-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90a4f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90a4f-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90a4f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90a4f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90a4f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
