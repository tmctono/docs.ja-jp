---
title: ICorDebugHandleValue::GetHandleType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: bc7d99d0ddb443cba227b7bad0cd53edb94c9101
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138540"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="e3840-102">ICorDebugHandleValue::GetHandleType メソッド</span><span class="sxs-lookup"><span data-stu-id="e3840-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="e3840-103">この値オブジェクトによって参照されるハンドルの種類を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e3840-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3840-104">構文</span><span class="sxs-lookup"><span data-stu-id="e3840-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3840-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3840-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="e3840-106">入出力このハンドルの型を示す CorDebugHandleType 列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e3840-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3840-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="e3840-107">Requirements</span></span>  
 <span data-ttu-id="e3840-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3840-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3840-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3840-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3840-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3840-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3840-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3840-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
