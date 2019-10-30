---
title: 'いい Exceptiondebugevent:: GetFlags メソッド'
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 6c330ce5b375daacdf257eda16fd5e34012f5d69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084753"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="32b8f-102">いい Exceptiondebugevent:: GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="32b8f-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="32b8f-103">例外をインターセプトできるかどうかを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="32b8f-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="32b8f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32b8f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="32b8f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="32b8f-106">入出力例外をインターセプトできるかどうかを示す[Cordebugexceptionflags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="32b8f-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32b8f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="32b8f-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32b8f-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="32b8f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32b8f-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="32b8f-109">Requirements</span></span>  
 <span data-ttu-id="32b8f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32b8f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32b8f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32b8f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32b8f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32b8f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32b8f-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32b8f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b8f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="32b8f-114">See also</span></span>

- [<span data-ttu-id="32b8f-115">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32b8f-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="32b8f-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32b8f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
