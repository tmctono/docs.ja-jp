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
ms.openlocfilehash: 3651a4be94fa624d0dd6ab64b8c3f8169945de0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175319"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="9523b-102">ICorDebugProcessEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9523b-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="9523b-103">ICorDebugEnum メソッドを実装し、ICorDebugProcess 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="9523b-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9523b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9523b-104">Methods</span></span>  
  
|<span data-ttu-id="9523b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9523b-105">Method</span></span>|<span data-ttu-id="9523b-106">説明</span><span class="sxs-lookup"><span data-stu-id="9523b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9523b-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="9523b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="9523b-108">指定した数を取得`ICorDebugProcess`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9523b-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9523b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9523b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9523b-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9523b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9523b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9523b-111">Requirements</span></span>  
 <span data-ttu-id="9523b-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9523b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9523b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9523b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9523b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9523b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9523b-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9523b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9523b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9523b-116">See also</span></span>

- [<span data-ttu-id="9523b-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9523b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
