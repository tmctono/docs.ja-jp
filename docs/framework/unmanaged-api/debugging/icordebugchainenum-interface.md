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
ms.openlocfilehash: 2d8a64b7dcaf4758cba217be06fa7d09f6c76920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989249"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="0bc81-102">ICorDebugChainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0bc81-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="0bc81-103">ICorDebugEnum のメソッドを実装し、ICorDebugChain 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="0bc81-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bc81-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0bc81-104">Methods</span></span>  
  
|<span data-ttu-id="0bc81-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0bc81-105">Method</span></span>|<span data-ttu-id="0bc81-106">説明</span><span class="sxs-lookup"><span data-stu-id="0bc81-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bc81-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="0bc81-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="0bc81-108">指定した数を取得`ICorDebugChain`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="0bc81-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bc81-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0bc81-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bc81-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0bc81-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bc81-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0bc81-111">Requirements</span></span>  
 <span data-ttu-id="0bc81-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc81-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc81-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bc81-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bc81-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bc81-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bc81-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc81-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bc81-116">See also</span></span>

- [<span data-ttu-id="0bc81-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0bc81-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
