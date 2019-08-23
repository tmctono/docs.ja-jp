---
title: ICorDebugFrameEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9ea398c32762be31f93002533b15bcf3851b870
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910241"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="2d4db-102">ICorDebugFrameEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d4db-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="2d4db-103">ICorDebugEnum メソッドを実装し、テキストボックスの配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="2d4db-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d4db-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d4db-104">Methods</span></span>  
  
|<span data-ttu-id="2d4db-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d4db-105">Method</span></span>|<span data-ttu-id="2d4db-106">説明</span><span class="sxs-lookup"><span data-stu-id="2d4db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d4db-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="2d4db-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="2d4db-108">現在の`ICorDebugFrame`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="2d4db-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d4db-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d4db-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d4db-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2d4db-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d4db-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d4db-111">Requirements</span></span>  
 <span data-ttu-id="2d4db-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d4db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d4db-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2d4db-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d4db-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="2d4db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d4db-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d4db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d4db-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d4db-116">See also</span></span>

- [<span data-ttu-id="2d4db-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d4db-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
