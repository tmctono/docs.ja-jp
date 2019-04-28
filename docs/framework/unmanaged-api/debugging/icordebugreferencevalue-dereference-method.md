---
title: ICorDebugReferenceValue::Dereference メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b436fa14322d444a6c8b515ba8e50698eecb95ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783020"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="8bc1c-102">ICorDebugReferenceValue::Dereference メソッド</span><span class="sxs-lookup"><span data-stu-id="8bc1c-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="8bc1c-103">参照されているオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bc1c-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bc1c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bc1c-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="8bc1c-106">[out]この ICorDebugReferenceValue オブジェクトが指し示すオブジェクトを表すアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc1c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8bc1c-107">Remarks</span></span>  
 <span data-ttu-id="8bc1c-108">`ICorDebugValue`オブジェクトが、その参照がまだ無効になっていない場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc1c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8bc1c-109">Requirements</span></span>  
 <span data-ttu-id="8bc1c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bc1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bc1c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bc1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bc1c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bc1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bc1c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bc1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
