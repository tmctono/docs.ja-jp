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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e41cf2ebf0cc64ee7cf720643ae3229cdfbad1ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969284"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="879a7-102">ICorDebugChainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="879a7-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="879a7-103">ICorDebugEnum メソッドを実装し、を列挙します。</span><span class="sxs-lookup"><span data-stu-id="879a7-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="879a7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="879a7-104">Methods</span></span>  
  
|<span data-ttu-id="879a7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="879a7-105">Method</span></span>|<span data-ttu-id="879a7-106">説明</span><span class="sxs-lookup"><span data-stu-id="879a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="879a7-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="879a7-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="879a7-108">現在の`ICorDebugChain`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="879a7-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="879a7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="879a7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="879a7-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="879a7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="879a7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="879a7-111">Requirements</span></span>  
 <span data-ttu-id="879a7-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="879a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="879a7-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="879a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="879a7-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="879a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="879a7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="879a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879a7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="879a7-116">See also</span></span>

- [<span data-ttu-id="879a7-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="879a7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
