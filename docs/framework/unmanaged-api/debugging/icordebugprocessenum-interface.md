---
title: ICorDebugProcessEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81653c69353b60d7287240505f53b26552c21774
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960987"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="a5a28-102">ICorDebugProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5a28-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="a5a28-103">ICorDebugEnum メソッドを実装し、を処理する配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="a5a28-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5a28-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5a28-104">Methods</span></span>  
  
|<span data-ttu-id="a5a28-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a5a28-105">Method</span></span>|<span data-ttu-id="a5a28-106">説明</span><span class="sxs-lookup"><span data-stu-id="a5a28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5a28-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a5a28-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="a5a28-108">現在の`ICorDebugProcess`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="a5a28-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5a28-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a5a28-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5a28-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a5a28-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a28-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a5a28-111">Requirements</span></span>  
 <span data-ttu-id="a5a28-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5a28-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a28-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a5a28-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5a28-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a5a28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5a28-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a28-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5a28-116">See also</span></span>

- [<span data-ttu-id="a5a28-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a5a28-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
