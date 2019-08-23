---
title: ICorDebugModuleEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 682fe190126d4f40013678d996804e9f3481bc02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965084"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="a83a4-102">ICorDebugModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a83a4-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="a83a4-103">ICorDebugEnum メソッドを実装し、モジュール配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="a83a4-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a83a4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a83a4-104">Methods</span></span>  
  
|<span data-ttu-id="a83a4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a83a4-105">Method</span></span>|<span data-ttu-id="a83a4-106">説明</span><span class="sxs-lookup"><span data-stu-id="a83a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a83a4-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a83a4-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="a83a4-108">現在の`ICorDebugModule`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="a83a4-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a83a4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a83a4-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a83a4-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a83a4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a83a4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a83a4-111">Requirements</span></span>  
 <span data-ttu-id="a83a4-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a83a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a83a4-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a83a4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a83a4-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a83a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a83a4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a83a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83a4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a83a4-116">See also</span></span>

- [<span data-ttu-id="a83a4-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a83a4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
