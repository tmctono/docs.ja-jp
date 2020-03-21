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
ms.openlocfilehash: 35e043c56977bf644efe1dd9cee1409f50cc877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179028"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="230fc-102">ICorDebugArrayValue::GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="230fc-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="230fc-103">この配列の各次元の要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="230fc-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="230fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="230fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="230fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="230fc-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="230fc-106">[in]このオブジェクトの次元の数。</span><span class="sxs-lookup"><span data-stu-id="230fc-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="230fc-107">この値は、オブジェクトの次元数`dims`と同じサイズであるため、配列の`ICorDebugArrayValue`サイズでもあります。</span><span class="sxs-lookup"><span data-stu-id="230fc-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="230fc-108">[アウト]整数の配列で、この`ICorDebugArrayValue`オブジェクト内の次元内の要素の数をそれぞれ指定します。</span><span class="sxs-lookup"><span data-stu-id="230fc-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="230fc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="230fc-109">Requirements</span></span>  
 <span data-ttu-id="230fc-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="230fc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="230fc-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="230fc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="230fc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="230fc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="230fc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="230fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
