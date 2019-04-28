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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49f5ed8b24d81ba8f32a9fe0ad7488693718bde9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645670"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="774c6-102">ICorDebugArrayValue::HasBaseIndicies メソッド</span><span class="sxs-lookup"><span data-stu-id="774c6-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="774c6-103">この配列のディメンションに 0 以外のベース インデックスがあるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="774c6-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="774c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="774c6-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="774c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="774c6-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="774c6-106">[out]ブール値へのポインター`true`場合この 1 つまたは複数のディメンション`ICorDebugArrayValue`オブジェクトは、0 以外の基本のインデックスを持つ。 ブール値は、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="774c6-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="774c6-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="774c6-107">Requirements</span></span>  
 <span data-ttu-id="774c6-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="774c6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="774c6-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="774c6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="774c6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="774c6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="774c6-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="774c6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
