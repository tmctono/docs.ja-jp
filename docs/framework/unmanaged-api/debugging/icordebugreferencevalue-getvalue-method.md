---
title: ICorDebugReferenceValue::GetValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e52ef20f2b8e3937911dc37e68f8a338ab0d85d9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468872"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="af0b9-102">ICorDebugReferenceValue::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="af0b9-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="af0b9-103">参照先オブジェクトの現在のメモリ アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="af0b9-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="af0b9-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af0b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af0b9-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="af0b9-106">[out]ポインターを`CORDB_ADDRESS`この ICorDebugReferenceValue オブジェクトが指すオブジェクトのアドレスを指定する値。</span><span class="sxs-lookup"><span data-stu-id="af0b9-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0b9-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="af0b9-107">Requirements</span></span>  
 <span data-ttu-id="af0b9-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0b9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af0b9-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af0b9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af0b9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af0b9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af0b9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af0b9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
