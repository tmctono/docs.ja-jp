---
title: ICorDebugArrayValue::GetDimensions メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: c5199794098e4d83588728eeb165aee5f81fe4c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088510"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="d48db-102">ICorDebugArrayValue::GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="d48db-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="d48db-103">この配列の各次元に含まれる要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="d48db-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48db-104">構文</span><span class="sxs-lookup"><span data-stu-id="d48db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d48db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d48db-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="d48db-106">からこの ICorDebugArrayValue オブジェクトの次元数。</span><span class="sxs-lookup"><span data-stu-id="d48db-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="d48db-107">この値は、サイズが `ICorDebugArrayValue` オブジェクトの次元数と同じであるため、`dims` 配列のサイズでもあります。</span><span class="sxs-lookup"><span data-stu-id="d48db-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="d48db-108">入出力整数の配列。各整数は、この `ICorDebugArrayValue` オブジェクトのディメンションに含まれる要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d48db-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d48db-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="d48db-109">Requirements</span></span>  
 <span data-ttu-id="d48db-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48db-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d48db-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d48db-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d48db-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d48db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d48db-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d48db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
