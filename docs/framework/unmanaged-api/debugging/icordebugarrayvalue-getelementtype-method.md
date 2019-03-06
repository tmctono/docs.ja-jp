---
title: ICorDebugArrayValue::GetElementType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6f5f1da94e1ae07a604a616c631a38d02caea9d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496197"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="6b114-102">ICorDebugArrayValue::GetElementType メソッド</span><span class="sxs-lookup"><span data-stu-id="6b114-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="6b114-103">配列内の要素の単純型を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b114-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b114-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b114-104">Syntax</span></span>  
  
```  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b114-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b114-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="6b114-106">[out]種類を示す CorElementType 列挙型の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6b114-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b114-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b114-107">Requirements</span></span>  
 <span data-ttu-id="6b114-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b114-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b114-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b114-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b114-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b114-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b114-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b114-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
