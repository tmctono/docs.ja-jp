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
ms.openlocfilehash: e6e8eb91bbc41faf0dcea010da9aa54995058653
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894975"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="a480e-102">ICorDebugArrayValue::HasBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="a480e-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="a480e-103">この配列のどの次元にも0以外のベースインデックスがあるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a480e-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a480e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a480e-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a480e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a480e-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="a480e-106">入出力この`ICorDebugArrayValue`オブジェクトの1つ以上の次元`true`に0以外のベースインデックスがある場合は、ブール値へのポインター。それ以外の場合、ブール`false`値はです。</span><span class="sxs-lookup"><span data-stu-id="a480e-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a480e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a480e-107">Requirements</span></span>  
 <span data-ttu-id="a480e-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a480e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a480e-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a480e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a480e-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a480e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a480e-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a480e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
