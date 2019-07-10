---
title: ICorDebug::Initialize メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80465c8d1f1f9e09c0675de1667b999b332b9f6b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738150"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="d69a4-102">ICorDebug::Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="d69a4-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="d69a4-103">`ICorDebug` オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="d69a4-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d69a4-104">構文</span><span class="sxs-lookup"><span data-stu-id="d69a4-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d69a4-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="d69a4-105">Remarks</span></span>  
 <span data-ttu-id="d69a4-106">デバッガーを呼び出す必要があります`Initialize`デバッグを初期化するために時間がサービスの作成時。</span><span class="sxs-lookup"><span data-stu-id="d69a4-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="d69a4-107">他のメソッドの前にこのメソッドを呼び出す必要があります`ICorDebug`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d69a4-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d69a4-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="d69a4-108">Requirements</span></span>  
 <span data-ttu-id="d69a4-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d69a4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d69a4-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d69a4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d69a4-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d69a4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d69a4-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d69a4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69a4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d69a4-113">See also</span></span>

- [<span data-ttu-id="d69a4-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d69a4-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
