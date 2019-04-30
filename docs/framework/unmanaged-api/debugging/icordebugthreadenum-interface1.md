---
title: ICorDebugThreadEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7edf103e397c6e3e1577b5ed4bc8fc0df264b843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993851"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="4328b-102">ICorDebugThreadEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4328b-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="4328b-103">ICorDebugEnum メソッドを実装し、ICorDebugThread 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="4328b-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4328b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4328b-104">Methods</span></span>  
  
|<span data-ttu-id="4328b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4328b-105">Method</span></span>|<span data-ttu-id="4328b-106">説明</span><span class="sxs-lookup"><span data-stu-id="4328b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4328b-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="4328b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="4328b-108">指定した数を取得`ICorDebugThread`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="4328b-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4328b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4328b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4328b-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4328b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4328b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4328b-111">Requirements</span></span>  
 <span data-ttu-id="4328b-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4328b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4328b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4328b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4328b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4328b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4328b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4328b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4328b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4328b-116">See also</span></span>

- [<span data-ttu-id="4328b-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4328b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
