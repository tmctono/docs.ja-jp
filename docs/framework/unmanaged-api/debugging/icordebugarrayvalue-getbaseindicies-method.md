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
ms.openlocfilehash: 9aadbe7c6f18c6b15350267d1f9ecaa3a23cdd20
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895066"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="84b2c-102">ICorDebugArrayValue::GetBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="84b2c-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="84b2c-103">配列内の各次元のベースインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="84b2c-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b2c-104">構文</span><span class="sxs-lookup"><span data-stu-id="84b2c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84b2c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84b2c-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="84b2c-106">からこの`ICorDebugArrayValue`オブジェクトの次元数。</span><span class="sxs-lookup"><span data-stu-id="84b2c-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="84b2c-107">この値は、 `indicies`配列のサイズが`ICorDebugArrayValue`オブジェクトの次元数と同じであるため、配列のサイズでもあります。</span><span class="sxs-lookup"><span data-stu-id="84b2c-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="84b2c-108">入出力整数の配列。各整数は、この`ICorDebugArrayValue`オブジェクトの次元のベースインデックス (つまり開始インデックス) です。</span><span class="sxs-lookup"><span data-stu-id="84b2c-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84b2c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="84b2c-109">Requirements</span></span>  
 <span data-ttu-id="84b2c-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84b2c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84b2c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84b2c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84b2c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84b2c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84b2c-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84b2c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
