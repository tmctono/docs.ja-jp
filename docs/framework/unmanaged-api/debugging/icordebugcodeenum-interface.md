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
ms.openlocfilehash: 6f36ce2fbf57c72102550069989c94b5cc19e58c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186655"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="666bc-102">ICorDebugCodeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="666bc-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="666bc-103">"ICorDebugEnum"のメソッドを実装し、"ICorDebugCode"配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="666bc-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="666bc-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="666bc-104">Methods</span></span>  
  
|<span data-ttu-id="666bc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="666bc-105">Method</span></span>|<span data-ttu-id="666bc-106">説明</span><span class="sxs-lookup"><span data-stu-id="666bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="666bc-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="666bc-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="666bc-108">指定した数を取得`ICorDebugCode`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="666bc-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="666bc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="666bc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="666bc-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="666bc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="666bc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="666bc-111">Requirements</span></span>  
 <span data-ttu-id="666bc-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="666bc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666bc-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="666bc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="666bc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="666bc-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="666bc-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="666bc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="666bc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="666bc-116">See also</span></span>

- [<span data-ttu-id="666bc-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="666bc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
