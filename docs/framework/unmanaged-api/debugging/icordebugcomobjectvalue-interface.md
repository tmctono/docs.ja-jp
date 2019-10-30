---
title: ICorDebugComObjectValue のインターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 4ff5c0d470e6eb84eb8b526f5e8f74e5e1a8118a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125488"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="45237-102">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="45237-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="45237-103">ランタイム呼び出し可能ラッパー (RCW) に関連付けられている情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="45237-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45237-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="45237-104">Methods</span></span>  
  
|<span data-ttu-id="45237-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="45237-105">Method</span></span>|<span data-ttu-id="45237-106">説明</span><span class="sxs-lookup"><span data-stu-id="45237-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45237-107">GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="45237-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="45237-108">現在の RCW でキャッシュされている生のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="45237-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="45237-109">GetCachedInterfaceTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="45237-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="45237-110">現在のオブジェクトで使用または使用されているインターフェイス型の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="45237-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45237-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="45237-111">Remarks</span></span>  
 <span data-ttu-id="45237-112">"ICorDebugValue" インターフェイスのインスタンスが RCW を表すかどうかを確認するには、デバッガーが `IID_ICorDebugComObjectValue`で "ICorDebugValue" に対して `QueryInterface` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45237-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45237-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="45237-113">Requirements</span></span>  
 <span data-ttu-id="45237-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45237-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45237-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45237-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45237-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45237-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45237-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45237-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45237-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="45237-118">See also</span></span>

- [<span data-ttu-id="45237-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45237-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="45237-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="45237-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
