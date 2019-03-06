---
title: ICorDebugBoxValue::GetObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c20eec52b0e4616af1b864bb58b6cbff44a720eb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490373"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="54b42-102">ICorDebugBoxValue::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="54b42-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="54b42-103">ボックス化された値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54b42-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b42-104">構文</span><span class="sxs-lookup"><span data-stu-id="54b42-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54b42-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54b42-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="54b42-106">[out]ボックス化された値を表す ICorDebugObjectValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="54b42-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b42-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="54b42-107">Requirements</span></span>  
 <span data-ttu-id="54b42-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b42-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b42-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54b42-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54b42-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54b42-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54b42-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54b42-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
