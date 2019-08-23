---
title: ICorDebugCodeEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a771100ad4d63173fdb3b1ddea5ae3d67fbbc7c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960675"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="1c365-102">ICorDebugCodeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c365-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="1c365-103">"ICorDebugEnum" メソッドを実装し、"コード" 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="1c365-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c365-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1c365-104">Methods</span></span>  
  
|<span data-ttu-id="1c365-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1c365-105">Method</span></span>|<span data-ttu-id="1c365-106">説明</span><span class="sxs-lookup"><span data-stu-id="1c365-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c365-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="1c365-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="1c365-108">現在の`ICorDebugCode`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="1c365-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c365-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c365-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c365-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1c365-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c365-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c365-111">Requirements</span></span>  
 <span data-ttu-id="1c365-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c365-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c365-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1c365-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c365-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="1c365-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c365-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c365-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c365-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c365-116">See also</span></span>

- [<span data-ttu-id="1c365-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c365-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
