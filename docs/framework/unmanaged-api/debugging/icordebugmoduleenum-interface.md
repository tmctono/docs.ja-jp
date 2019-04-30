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
ms.openlocfilehash: 26efb3e43642b6d1fd10b084c2b321609c89d89b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994683"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="6b76c-102">ICorDebugModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b76c-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="6b76c-103">ICorDebugEnum のメソッドを実装し、ICorDebugModule 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="6b76c-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b76c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b76c-104">Methods</span></span>  
  
|<span data-ttu-id="6b76c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b76c-105">Method</span></span>|<span data-ttu-id="6b76c-106">説明</span><span class="sxs-lookup"><span data-stu-id="6b76c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b76c-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="6b76c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="6b76c-108">指定した数を取得`ICorDebugModule`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6b76c-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b76c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b76c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b76c-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b76c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b76c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b76c-111">Requirements</span></span>  
 <span data-ttu-id="6b76c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b76c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b76c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b76c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b76c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b76c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b76c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b76c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b76c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b76c-116">See also</span></span>

- [<span data-ttu-id="6b76c-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b76c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
