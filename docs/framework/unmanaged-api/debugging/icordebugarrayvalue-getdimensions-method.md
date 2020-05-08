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
ms.openlocfilehash: fa2be894af6e44d09c25a736f45acba56052f9fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895041"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="2320a-102">ICorDebugArrayValue::GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="2320a-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="2320a-103">この配列の各次元に含まれる要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="2320a-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2320a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2320a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2320a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2320a-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="2320a-106">からこの ICorDebugArrayValue オブジェクトの次元数。</span><span class="sxs-lookup"><span data-stu-id="2320a-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="2320a-107">この値は、 `dims`配列のサイズが`ICorDebugArrayValue`オブジェクトの次元数と同じであるため、配列のサイズでもあります。</span><span class="sxs-lookup"><span data-stu-id="2320a-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="2320a-108">入出力整数の配列。各整数は、この`ICorDebugArrayValue`オブジェクト内のディメンション内の要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2320a-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2320a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2320a-109">Requirements</span></span>  
 <span data-ttu-id="2320a-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2320a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2320a-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2320a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2320a-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2320a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2320a-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2320a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
