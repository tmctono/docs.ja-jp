---
title: ICorDebugThreadEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b7e5b0a9f4166923a559eb3886aa0f9cabbcd72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962948"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="ee8f0-102">ICorDebugThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee8f0-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="ee8f0-103">ICorDebugEnum メソッドを実装し、の各スレッド配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="ee8f0-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee8f0-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ee8f0-104">Methods</span></span>  
  
|<span data-ttu-id="ee8f0-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ee8f0-105">Method</span></span>|<span data-ttu-id="ee8f0-106">説明</span><span class="sxs-lookup"><span data-stu-id="ee8f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee8f0-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="ee8f0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="ee8f0-108">現在の`ICorDebugThread`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="ee8f0-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee8f0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee8f0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee8f0-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ee8f0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee8f0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee8f0-111">Requirements</span></span>  
 <span data-ttu-id="ee8f0-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee8f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee8f0-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ee8f0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee8f0-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="ee8f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee8f0-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee8f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee8f0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee8f0-116">See also</span></span>

- [<span data-ttu-id="ee8f0-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ee8f0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
