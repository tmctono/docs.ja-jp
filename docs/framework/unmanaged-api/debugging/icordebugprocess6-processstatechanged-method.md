---
title: ICorDebugProcess6::ProcessStateChanged メソッド
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: b6665df550a2d07a3fa84c3f2b6bf07f459cd713
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792200"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="6ecc4-102">ICorDebugProcess6::ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="6ecc4-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="6ecc4-103">プロセスが実行されていることを[ICorDebug](icordebug-interface.md)に通知します。</span><span class="sxs-lookup"><span data-stu-id="6ecc4-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ecc4-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ecc4-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ecc4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ecc4-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="6ecc4-106">から[ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)列挙型のメンバー</span><span class="sxs-lookup"><span data-stu-id="6ecc4-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ecc4-107">コメント</span><span class="sxs-lookup"><span data-stu-id="6ecc4-107">Remarks</span></span>  
 <span data-ttu-id="6ecc4-108">デバッガーはこのメソッドを呼び出して、プロセスが実行されていることを[ICorDebug](icordebug-interface.md)に通知します。</span><span class="sxs-lookup"><span data-stu-id="6ecc4-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ecc4-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ecc4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ecc4-110">要件</span><span class="sxs-lookup"><span data-stu-id="6ecc4-110">Requirements</span></span>  
 <span data-ttu-id="6ecc4-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecc4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ecc4-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ecc4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ecc4-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ecc4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ecc4-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecc4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecc4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ecc4-115">See also</span></span>

- [<span data-ttu-id="6ecc4-116">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ecc4-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="6ecc4-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ecc4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
