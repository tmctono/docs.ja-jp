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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21703aa911b5222fff71282e6da26aa5c0e2853
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756856"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="ab22b-102">ICorDebugHandleValue::Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="ab22b-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="ab22b-103">インターフェイス ポインターを明示的に解放せずにこの ICorDebugHandleValue オブジェクトによって参照されるハンドルを解放します。</span><span class="sxs-lookup"><span data-stu-id="ab22b-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab22b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab22b-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="ab22b-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab22b-105">Requirements</span></span>  
 <span data-ttu-id="ab22b-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab22b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab22b-107">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab22b-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab22b-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab22b-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab22b-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab22b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
