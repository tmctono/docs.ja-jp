---
title: ICorDebugDebugEvent::GetThread メソッド
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f85dccd5b59610c52adcf685828984c9344fd49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911281"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="98235-102">ICorDebugDebugEvent::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="98235-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="98235-103">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="98235-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98235-104">構文</span><span class="sxs-lookup"><span data-stu-id="98235-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98235-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98235-105">Parameters</span></span>  
 <span data-ttu-id="98235-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="98235-106">ppThread</span></span>  
 <span data-ttu-id="98235-107">入出力イベントが発生したスレッドを表す、のスレッドオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="98235-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98235-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="98235-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98235-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="98235-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98235-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="98235-110">Requirements</span></span>  
 <span data-ttu-id="98235-111">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98235-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98235-112">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="98235-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98235-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="98235-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98235-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98235-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98235-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="98235-115">See also</span></span>

- [<span data-ttu-id="98235-116">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98235-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="98235-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98235-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
