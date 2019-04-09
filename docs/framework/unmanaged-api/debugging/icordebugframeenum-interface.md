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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093827"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="42be6-102">ICorDebugFrameEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42be6-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="42be6-103">ICorDebugEnum のメソッドを実装し、ICorDebugFrame 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="42be6-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42be6-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="42be6-104">Methods</span></span>  
  
|<span data-ttu-id="42be6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="42be6-105">Method</span></span>|<span data-ttu-id="42be6-106">説明</span><span class="sxs-lookup"><span data-stu-id="42be6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42be6-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="42be6-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="42be6-108">指定した数を取得`ICorDebugFrame`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="42be6-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42be6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="42be6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42be6-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="42be6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42be6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="42be6-111">Requirements</span></span>  
 <span data-ttu-id="42be6-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42be6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42be6-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42be6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42be6-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42be6-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="42be6-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="42be6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42be6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="42be6-116">See also</span></span>

- [<span data-ttu-id="42be6-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="42be6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
