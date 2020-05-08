---
title: ICorDebugDebugEvent::GetThread メソッド
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: acce18517c105739417fc734b49ff004ca9546dc
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976379"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="1ce41-102">ICorDebugDebugEvent::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="1ce41-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="1ce41-103">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ce41-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce41-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ce41-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce41-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ce41-105">Parameters</span></span>  
 <span data-ttu-id="1ce41-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="1ce41-106">ppThread</span></span>  
 <span data-ttu-id="1ce41-107">[出力] イベントが発生したスレッドを表す ICorDebugThread オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ce41-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ce41-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ce41-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ce41-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ce41-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ce41-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ce41-110">Requirements</span></span>  
 <span data-ttu-id="1ce41-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce41-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce41-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ce41-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ce41-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ce41-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ce41-114">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce41-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce41-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ce41-115">See also</span></span>

- [<span data-ttu-id="1ce41-116">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ce41-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="1ce41-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ce41-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
