---
title: ICorDebugDebugEvent::GetThread メソッド
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 66b4abc4bebfbbde2e6a6b25d2bc0e88839a363f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136647"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="18a62-102">ICorDebugDebugEvent::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="18a62-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="18a62-103">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="18a62-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a62-104">構文</span><span class="sxs-lookup"><span data-stu-id="18a62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18a62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18a62-105">Parameters</span></span>  
 <span data-ttu-id="18a62-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="18a62-106">ppThread</span></span>  
 <span data-ttu-id="18a62-107">入出力イベントが発生したスレッドを表す、のスレッドオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18a62-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18a62-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="18a62-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18a62-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="18a62-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a62-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="18a62-110">Requirements</span></span>  
 <span data-ttu-id="18a62-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18a62-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a62-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18a62-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18a62-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18a62-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18a62-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18a62-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a62-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="18a62-115">See also</span></span>

- [<span data-ttu-id="18a62-116">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18a62-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="18a62-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18a62-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
