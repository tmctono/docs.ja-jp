---
title: ICorDebugDebugEvent::GetEventKind メソッド
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a87dda8d8a263df1989a685d94c5163212f41382
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911341"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="af0ff-102">ICorDebugDebugEvent::GetEventKind メソッド</span><span class="sxs-lookup"><span data-stu-id="af0ff-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="af0ff-103">この `ICorDebugDebugEvent` オブジェクトが表すイベントの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="af0ff-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="af0ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af0ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af0ff-105">Parameters</span></span>  
 <span data-ttu-id="af0ff-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="af0ff-106">pDebugEventKind</span></span>  
 <span data-ttu-id="af0ff-107">イベントの種類を示す[Cordebugdebugeventkind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)列挙体メンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="af0ff-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af0ff-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="af0ff-108">Remarks</span></span>  
 <span data-ttu-id="af0ff-109">`pDebugEventKind` の値に基づいて、`QueryInterface` を呼び出して、追加データを含むより正確なデバッグ イベント インターフェイスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="af0ff-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af0ff-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af0ff-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0ff-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="af0ff-111">Requirements</span></span>  
 <span data-ttu-id="af0ff-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af0ff-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="af0ff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af0ff-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="af0ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af0ff-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af0ff-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0ff-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af0ff-116">See also</span></span>

- [<span data-ttu-id="af0ff-117">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af0ff-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="af0ff-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af0ff-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
