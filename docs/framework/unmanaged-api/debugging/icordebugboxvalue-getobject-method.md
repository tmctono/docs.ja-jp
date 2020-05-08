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
ms.openlocfilehash: 401f052b881c1a0cfa065ba60c93aca1706f34f4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894781"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="50f3a-102">ICorDebugBoxValue::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="50f3a-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="50f3a-103">ボックス化された値を取得します。</span><span class="sxs-lookup"><span data-stu-id="50f3a-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="50f3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50f3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50f3a-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="50f3a-106">入出力ボックス化された値を表す、ボックス化された値を表すオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="50f3a-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f3a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="50f3a-107">Requirements</span></span>  
 <span data-ttu-id="50f3a-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50f3a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50f3a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50f3a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50f3a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50f3a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50f3a-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50f3a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
