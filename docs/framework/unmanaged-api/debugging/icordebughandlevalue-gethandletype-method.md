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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecc0b46618cd00ba4442e30c23a7b7e950382fee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475594"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="92a8b-102">ICorDebugHandleValue::GetHandleType メソッド</span><span class="sxs-lookup"><span data-stu-id="92a8b-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="92a8b-103">ICorDebugHandleValue オブジェクトによって参照されているハンドルの種類を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="92a8b-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a8b-104">構文</span><span class="sxs-lookup"><span data-stu-id="92a8b-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92a8b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92a8b-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="92a8b-106">[out]このハンドルの種類を示す CorDebugHandleType 列挙型の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="92a8b-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a8b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="92a8b-107">Requirements</span></span>  
 <span data-ttu-id="92a8b-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a8b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92a8b-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92a8b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92a8b-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92a8b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92a8b-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92a8b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
