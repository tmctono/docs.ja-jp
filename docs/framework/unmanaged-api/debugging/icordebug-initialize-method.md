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
ms.openlocfilehash: 3d27cf1987d7e9896885f87857554f4039c8d714
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788977"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="d9259-102">ICorDebug::Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="d9259-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="d9259-103">`ICorDebug` オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="d9259-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9259-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9259-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d9259-105">コメント</span><span class="sxs-lookup"><span data-stu-id="d9259-105">Remarks</span></span>  
 <span data-ttu-id="d9259-106">デバッガーは、作成時に `Initialize` を呼び出して、デバッグサービスを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9259-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="d9259-107">`ICorDebug` の他のメソッドが呼び出される前に、このメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9259-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9259-108">要件</span><span class="sxs-lookup"><span data-stu-id="d9259-108">Requirements</span></span>  
 <span data-ttu-id="d9259-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9259-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9259-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9259-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9259-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9259-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9259-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9259-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9259-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9259-113">See also</span></span>

- [<span data-ttu-id="d9259-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9259-114">ICorDebug Interface</span></span>](icordebug-interface.md)
