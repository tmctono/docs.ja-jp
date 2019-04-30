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
ms.openlocfilehash: cd24dfa6771ca450e79b4b932735968ecc51fc90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995788"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="30e67-102">ICorDebugFrameEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30e67-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="30e67-103">ICorDebugEnum のメソッドを実装し、ICorDebugFrame 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="30e67-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30e67-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="30e67-104">Methods</span></span>  
  
|<span data-ttu-id="30e67-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="30e67-105">Method</span></span>|<span data-ttu-id="30e67-106">説明</span><span class="sxs-lookup"><span data-stu-id="30e67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30e67-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="30e67-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="30e67-108">指定した数を取得`ICorDebugFrame`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="30e67-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e67-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="30e67-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30e67-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="30e67-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e67-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="30e67-111">Requirements</span></span>  
 <span data-ttu-id="30e67-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e67-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30e67-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30e67-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30e67-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30e67-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e67-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="30e67-116">See also</span></span>

- [<span data-ttu-id="30e67-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30e67-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
