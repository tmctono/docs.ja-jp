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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749801"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="31956-102">ICorDebugCodeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31956-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="31956-103">"ICorDebugEnum"のメソッドを実装し、"ICorDebugCode"配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="31956-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31956-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="31956-104">Methods</span></span>  
  
|<span data-ttu-id="31956-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="31956-105">Method</span></span>|<span data-ttu-id="31956-106">説明</span><span class="sxs-lookup"><span data-stu-id="31956-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31956-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="31956-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="31956-108">指定した数を取得`ICorDebugCode`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="31956-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31956-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="31956-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31956-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="31956-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31956-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="31956-111">Requirements</span></span>  
 <span data-ttu-id="31956-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31956-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31956-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31956-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31956-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31956-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31956-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31956-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31956-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="31956-116">See also</span></span>

- [<span data-ttu-id="31956-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31956-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
