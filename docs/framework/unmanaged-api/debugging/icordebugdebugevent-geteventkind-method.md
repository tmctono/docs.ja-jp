---
title: ICorDebugDebugEvent::GetEventKind メソッド
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 0c67f8bdce49b4e9200b501aaf00ae293cced7d7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783411"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="40683-102">ICorDebugDebugEvent::GetEventKind メソッド</span><span class="sxs-lookup"><span data-stu-id="40683-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="40683-103">この `ICorDebugDebugEvent` オブジェクトが表すイベントの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="40683-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40683-104">構文</span><span class="sxs-lookup"><span data-stu-id="40683-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40683-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40683-105">Parameters</span></span>  
 <span data-ttu-id="40683-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="40683-106">pDebugEventKind</span></span>  
 <span data-ttu-id="40683-107">イベントの種類を示す[Cordebugdebugeventkind](cordebugdebugeventkind-enumeration.md)列挙体メンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40683-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40683-108">コメント</span><span class="sxs-lookup"><span data-stu-id="40683-108">Remarks</span></span>  
 <span data-ttu-id="40683-109">`pDebugEventKind` の値に基づいて、`QueryInterface` を呼び出して、追加データを含むより正確なデバッグ イベント インターフェイスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="40683-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40683-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="40683-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40683-111">要件</span><span class="sxs-lookup"><span data-stu-id="40683-111">Requirements</span></span>  
 <span data-ttu-id="40683-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40683-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40683-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40683-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40683-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40683-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40683-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40683-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40683-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="40683-116">See also</span></span>

- [<span data-ttu-id="40683-117">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40683-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="40683-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40683-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
