---
title: ICorDebugDebugEvent::GetThread メソッド
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793531"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="87e06-102">ICorDebugDebugEvent::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="87e06-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="87e06-103">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="87e06-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e06-104">構文</span><span class="sxs-lookup"><span data-stu-id="87e06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87e06-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87e06-105">Parameters</span></span>  
 <span data-ttu-id="87e06-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="87e06-106">ppThread</span></span>  
 <span data-ttu-id="87e06-107">[出力] イベントが発生したスレッドを表す ICorDebugThread オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="87e06-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87e06-108">コメント</span><span class="sxs-lookup"><span data-stu-id="87e06-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87e06-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="87e06-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e06-110">要件</span><span class="sxs-lookup"><span data-stu-id="87e06-110">Requirements</span></span>  
 <span data-ttu-id="87e06-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87e06-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e06-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87e06-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87e06-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87e06-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87e06-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e06-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e06-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="87e06-115">See also</span></span>

- [<span data-ttu-id="87e06-116">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87e06-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="87e06-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87e06-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
