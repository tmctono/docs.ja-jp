---
title: ICorDebugValueEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9484f211ff31c4fa71692db646ef3c556df0acad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171939"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="863c9-102">ICorDebugValueEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="863c9-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="863c9-103">"ICorDebugEnum"メソッドを実装し、"ICorDebugValue"配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="863c9-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="863c9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="863c9-104">Methods</span></span>  
  
|<span data-ttu-id="863c9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="863c9-105">Method</span></span>|<span data-ttu-id="863c9-106">説明</span><span class="sxs-lookup"><span data-stu-id="863c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="863c9-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="863c9-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-next-method.md)|<span data-ttu-id="863c9-108">指定した数を取得`ICorDebugValue`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="863c9-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="863c9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="863c9-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="863c9-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="863c9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="863c9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="863c9-111">Requirements</span></span>  
 <span data-ttu-id="863c9-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="863c9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="863c9-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="863c9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="863c9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="863c9-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="863c9-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="863c9-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="863c9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="863c9-116">See also</span></span>

- [<span data-ttu-id="863c9-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="863c9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
