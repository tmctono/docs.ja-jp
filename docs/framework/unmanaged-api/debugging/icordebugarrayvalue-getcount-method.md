---
title: ICorDebugArrayValue::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
ms.openlocfilehash: 82f282630a2e31b8c67d43fa0f0b30431a0d6ee4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895052"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="0cddc-102">ICorDebugArrayValue::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="0cddc-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="0cddc-103">配列内の要素の合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="0cddc-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cddc-104">構文</span><span class="sxs-lookup"><span data-stu-id="0cddc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cddc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0cddc-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="0cddc-106">入出力配列内の要素の合計数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0cddc-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cddc-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="0cddc-107">Requirements</span></span>  
 <span data-ttu-id="0cddc-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cddc-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cddc-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cddc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cddc-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cddc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cddc-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cddc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
