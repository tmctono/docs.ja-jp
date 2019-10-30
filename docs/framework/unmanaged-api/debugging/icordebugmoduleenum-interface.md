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
ms.openlocfilehash: eaf00369cf77aaa1ba16879bae1b74aba2eb9eab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123541"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="f8b35-102">ICorDebugModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f8b35-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="f8b35-103">ICorDebugEnum メソッドを実装し、モジュール配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="f8b35-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8b35-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f8b35-104">Methods</span></span>  
  
|<span data-ttu-id="f8b35-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f8b35-105">Method</span></span>|<span data-ttu-id="f8b35-106">説明</span><span class="sxs-lookup"><span data-stu-id="f8b35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8b35-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f8b35-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="f8b35-108">現在の位置から開始して、指定した数の `ICorDebugModule` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="f8b35-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8b35-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f8b35-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8b35-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f8b35-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8b35-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="f8b35-111">Requirements</span></span>  
 <span data-ttu-id="f8b35-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b35-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8b35-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8b35-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8b35-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8b35-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8b35-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8b35-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b35-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8b35-116">See also</span></span>

- [<span data-ttu-id="f8b35-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f8b35-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
