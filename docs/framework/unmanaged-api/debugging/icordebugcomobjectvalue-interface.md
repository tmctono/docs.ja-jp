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
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783973"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="f246b-102">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f246b-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="f246b-103">ランタイム呼び出し可能ラッパー (RCW) に関連付けられている情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f246b-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f246b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f246b-104">Methods</span></span>  
  
|<span data-ttu-id="f246b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f246b-105">Method</span></span>|<span data-ttu-id="f246b-106">説明</span><span class="sxs-lookup"><span data-stu-id="f246b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f246b-107">GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="f246b-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="f246b-108">現在の RCW でキャッシュされている生のインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f246b-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="f246b-109">GetCachedInterfaceTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="f246b-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="f246b-110">現在のオブジェクトで使用または使用されているインターフェイス型の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="f246b-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f246b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="f246b-111">Remarks</span></span>  
 <span data-ttu-id="f246b-112">"ICorDebugValue" インターフェイスのインスタンスが RCW を表すかどうかを確認するには、デバッガーが `IID_ICorDebugComObjectValue`で "ICorDebugValue" に対して `QueryInterface` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f246b-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f246b-113">要件</span><span class="sxs-lookup"><span data-stu-id="f246b-113">Requirements</span></span>  
 <span data-ttu-id="f246b-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f246b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f246b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f246b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f246b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f246b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f246b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f246b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f246b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f246b-118">See also</span></span>

- [<span data-ttu-id="f246b-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f246b-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f246b-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f246b-120">Debugging</span></span>](index.md)
