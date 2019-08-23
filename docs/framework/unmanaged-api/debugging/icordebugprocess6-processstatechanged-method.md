---
title: ICorDebugProcess6::ProcessStateChanged メソッド
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb158b383745cd7e44c8fede6ddd43ae81ced2d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930764"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="f8023-102">ICorDebugProcess6::ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="f8023-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="f8023-103">プロセスが実行されていることを[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)に通知します。</span><span class="sxs-lookup"><span data-stu-id="f8023-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8023-104">構文</span><span class="sxs-lookup"><span data-stu-id="f8023-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8023-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8023-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="f8023-106">から[ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)列挙型のメンバー</span><span class="sxs-lookup"><span data-stu-id="f8023-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8023-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f8023-107">Remarks</span></span>  
 <span data-ttu-id="f8023-108">デバッガーはこのメソッドを呼び出して、プロセスが実行されていることを[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)に通知します。</span><span class="sxs-lookup"><span data-stu-id="f8023-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8023-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8023-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8023-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f8023-110">Requirements</span></span>  
 <span data-ttu-id="f8023-111">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8023-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8023-112">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f8023-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8023-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="f8023-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8023-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8023-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8023-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8023-115">See also</span></span>

- [<span data-ttu-id="f8023-116">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f8023-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="f8023-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f8023-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
