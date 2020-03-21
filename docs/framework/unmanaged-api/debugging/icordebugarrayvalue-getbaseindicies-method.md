---
title: ICorDebugArrayValue::GetBaseIndicies メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179031"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="a2bbc-102">ICorDebugArrayValue::GetBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="a2bbc-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="a2bbc-103">配列内の各次元の基本インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a2bbc-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2bbc-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2bbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2bbc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2bbc-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="a2bbc-106">[in]この`ICorDebugArrayValue`オブジェクトの次元数。</span><span class="sxs-lookup"><span data-stu-id="a2bbc-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="a2bbc-107">この値は、オブジェクトの次元数`indicies`と同じサイズであるため、配列の`ICorDebugArrayValue`サイズでもあります。</span><span class="sxs-lookup"><span data-stu-id="a2bbc-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="a2bbc-108">[アウト]整数の配列で、各整数は、この`ICorDebugArrayValue`オブジェクトの次元の基本インデックス (開始インデックス) です。</span><span class="sxs-lookup"><span data-stu-id="a2bbc-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2bbc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2bbc-109">Requirements</span></span>  
 <span data-ttu-id="a2bbc-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2bbc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2bbc-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2bbc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2bbc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2bbc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2bbc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2bbc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
