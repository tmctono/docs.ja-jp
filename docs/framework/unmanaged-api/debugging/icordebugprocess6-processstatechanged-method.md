---
title: ICorDebugProcess6::ProcessStateChanged メソッド
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123415"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="b74a1-102">ICorDebugProcess6::ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="b74a1-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="b74a1-103">プロセスが実行されていることを[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)に通知します。</span><span class="sxs-lookup"><span data-stu-id="b74a1-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b74a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="b74a1-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b74a1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b74a1-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="b74a1-106">から[ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)列挙型のメンバー</span><span class="sxs-lookup"><span data-stu-id="b74a1-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b74a1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b74a1-107">Remarks</span></span>  
 <span data-ttu-id="b74a1-108">デバッガーはこのメソッドを呼び出して、プロセスが実行されていることを[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)に通知します。</span><span class="sxs-lookup"><span data-stu-id="b74a1-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b74a1-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b74a1-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b74a1-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="b74a1-110">Requirements</span></span>  
 <span data-ttu-id="b74a1-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b74a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b74a1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b74a1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b74a1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b74a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b74a1-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b74a1-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74a1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b74a1-115">See also</span></span>

- [<span data-ttu-id="b74a1-116">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b74a1-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="b74a1-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b74a1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
