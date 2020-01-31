---
title: ICorDebugValueEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: ba61df045caa117acae3756eb879cf67d0791222
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791061"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="312d7-102">ICorDebugValueEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="312d7-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="312d7-103">"ICorDebugEnum" メソッドを実装し、"ICorDebugValue" 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="312d7-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="312d7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="312d7-104">Methods</span></span>  
  
|<span data-ttu-id="312d7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="312d7-105">Method</span></span>|<span data-ttu-id="312d7-106">説明</span><span class="sxs-lookup"><span data-stu-id="312d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="312d7-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="312d7-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="312d7-108">現在の位置から開始して、指定した数の `ICorDebugValue` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="312d7-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="312d7-109">コメント</span><span class="sxs-lookup"><span data-stu-id="312d7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="312d7-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="312d7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="312d7-111">要件</span><span class="sxs-lookup"><span data-stu-id="312d7-111">Requirements</span></span>  
 <span data-ttu-id="312d7-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="312d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="312d7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="312d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="312d7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="312d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="312d7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="312d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312d7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="312d7-116">See also</span></span>

- [<span data-ttu-id="312d7-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="312d7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
