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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52075f33d594787c516f84b65b3319991380907
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645696"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="de918-102">ICorDebugArrayValue::GetDimensions メソッド</span><span class="sxs-lookup"><span data-stu-id="de918-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="de918-103">この配列の各次元の要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="de918-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de918-104">構文</span><span class="sxs-lookup"><span data-stu-id="de918-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de918-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de918-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="de918-106">[in]この ICorDebugArrayValue オブジェクトの次元数。</span><span class="sxs-lookup"><span data-stu-id="de918-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="de918-107">この値のサイズでも、`dims`配列のサイズがの次元数と等しいので、`ICorDebugArrayValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="de918-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="de918-108">[out]このディメンションの要素の数を指定の整数の配列`ICorDebugArrayValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="de918-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de918-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="de918-109">Requirements</span></span>  
 <span data-ttu-id="de918-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de918-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de918-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de918-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de918-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de918-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de918-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de918-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
