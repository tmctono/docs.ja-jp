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
ms.openlocfilehash: ed18f969d4ee857aee72668cf7230aa385586bde
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965242"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="2ba9f-102">ICorDebugCodeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ba9f-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="2ba9f-103">"ICorDebugEnum"のメソッドを実装し、"ICorDebugCode"配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="2ba9f-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ba9f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba9f-104">Methods</span></span>  
  
|<span data-ttu-id="2ba9f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba9f-105">Method</span></span>|<span data-ttu-id="2ba9f-106">説明</span><span class="sxs-lookup"><span data-stu-id="2ba9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ba9f-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba9f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="2ba9f-108">指定した数を取得`ICorDebugCode`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="2ba9f-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ba9f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ba9f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ba9f-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2ba9f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba9f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ba9f-111">Requirements</span></span>  
 <span data-ttu-id="2ba9f-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba9f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba9f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ba9f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ba9f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ba9f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ba9f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba9f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba9f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ba9f-116">See also</span></span>
- [<span data-ttu-id="2ba9f-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ba9f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
