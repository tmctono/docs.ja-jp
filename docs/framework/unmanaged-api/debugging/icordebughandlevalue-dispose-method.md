---
title: ICorDebugHandleValue::Dispose メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
ms.openlocfilehash: ff24ec418f4cd106fb35a61a134a69e5d60519b9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212179"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="dc5c4-102">ICorDebugHandleValue::Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="dc5c4-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="dc5c4-103">インターフェイスポインターを明示的に解放せずに、このオブジェクトによって参照されるハンドルを解放します。</span><span class="sxs-lookup"><span data-stu-id="dc5c4-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc5c4-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="dc5c4-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc5c4-105">Requirements</span></span>  
 <span data-ttu-id="dc5c4-106">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc5c4-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc5c4-107">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc5c4-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc5c4-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc5c4-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc5c4-109">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc5c4-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
