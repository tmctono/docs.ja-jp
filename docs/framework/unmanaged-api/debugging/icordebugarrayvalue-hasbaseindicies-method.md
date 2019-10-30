---
title: ICorDebugArrayValue::HasBaseIndicies メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: 418ebb51df3f2d86011ee2e77022c3ee5c7ac0b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088229"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="6dd1f-102">ICorDebugArrayValue::HasBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="6dd1f-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="6dd1f-103">この配列のどの次元にも0以外のベースインデックスがあるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6dd1f-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dd1f-104">構文</span><span class="sxs-lookup"><span data-stu-id="6dd1f-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dd1f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6dd1f-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="6dd1f-106">入出力この `ICorDebugArrayValue` オブジェクトの1つ以上の次元のベースインデックスが0以外の場合に `true` されるブール値へのポインター。それ以外の場合、ブール値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="6dd1f-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dd1f-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="6dd1f-107">Requirements</span></span>  
 <span data-ttu-id="6dd1f-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dd1f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dd1f-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6dd1f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6dd1f-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dd1f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dd1f-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dd1f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
