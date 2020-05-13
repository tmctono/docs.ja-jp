---
title: ICorDebugReferenceValue::IsNull メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: e8b778c0880040f5ffd639a445fd5663ce493219
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379081"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="4259f-102">ICorDebugReferenceValue::IsNull メソッド</span><span class="sxs-lookup"><span data-stu-id="4259f-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="4259f-103">この値が null 値であるかどうかを示す値を取得します。この場合、は `ICorDebugReferenceValue` オブジェクトを指していません。</span><span class="sxs-lookup"><span data-stu-id="4259f-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4259f-104">構文</span><span class="sxs-lookup"><span data-stu-id="4259f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4259f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4259f-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="4259f-106">入出力このオブジェクトが null の場合はとなるブール値へのポインター。 `true` `ICorDebugReferenceValue` それ以外の場合は `pbNull` `false` 。</span><span class="sxs-lookup"><span data-stu-id="4259f-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4259f-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="4259f-107">Requirements</span></span>  
 <span data-ttu-id="4259f-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4259f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4259f-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4259f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4259f-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4259f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4259f-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4259f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
