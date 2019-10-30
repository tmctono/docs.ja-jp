---
title: ICorDebugCode3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: f3ae25f7d16600a1b09f30f96a191d7ecf76713e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121060"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="135e9-102">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="135e9-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="135e9-103">"" のコード "と" ICorDebugCode2 "を拡張して、マネージ戻り値に関する情報を提供するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="135e9-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="135e9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="135e9-104">Methods</span></span>  
  
|<span data-ttu-id="135e9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="135e9-105">Method</span></span>|<span data-ttu-id="135e9-106">説明</span><span class="sxs-lookup"><span data-stu-id="135e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="135e9-107">GetReturnValueLiveOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="135e9-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="135e9-108">指定した IL オフセットについて、デバッガーが関数からの戻り値を取得できるように、ブレークポイントを配置する必要があるネイティブなオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="135e9-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="135e9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="135e9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="135e9-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="135e9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="135e9-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="135e9-111">Requirements</span></span>  
 <span data-ttu-id="135e9-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="135e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="135e9-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="135e9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="135e9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="135e9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="135e9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="135e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="135e9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="135e9-116">See also</span></span>

- [<span data-ttu-id="135e9-117">ICorDebugILFrame3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="135e9-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [<span data-ttu-id="135e9-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="135e9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
