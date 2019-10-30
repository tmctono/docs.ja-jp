---
title: ICorDebugChainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
ms.openlocfilehash: 63588a3d33577ff58c99e796e8e5453d2a6a9381
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123809"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="dff45-102">ICorDebugChainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dff45-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="dff45-103">ICorDebugEnum メソッドを実装し、を列挙します。</span><span class="sxs-lookup"><span data-stu-id="dff45-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dff45-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="dff45-104">Methods</span></span>  
  
|<span data-ttu-id="dff45-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dff45-105">Method</span></span>|<span data-ttu-id="dff45-106">説明</span><span class="sxs-lookup"><span data-stu-id="dff45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dff45-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="dff45-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="dff45-108">現在の位置から開始して、指定した数の `ICorDebugChain` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="dff45-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dff45-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="dff45-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dff45-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="dff45-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff45-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="dff45-111">Requirements</span></span>  
 <span data-ttu-id="dff45-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff45-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff45-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dff45-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dff45-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dff45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dff45-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff45-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dff45-116">See also</span></span>

- [<span data-ttu-id="dff45-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dff45-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
