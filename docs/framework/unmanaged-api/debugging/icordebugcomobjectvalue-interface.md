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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3387985ebf6027b9cd9dee372190da65939dbae3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098625"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="869a3-102">ICorDebugComObjectValue のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="869a3-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="869a3-103">ランタイム呼び出し可能ラッパー (RCW) に関連付けられている情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="869a3-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="869a3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="869a3-104">Methods</span></span>  
  
|<span data-ttu-id="869a3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="869a3-105">Method</span></span>|<span data-ttu-id="869a3-106">説明</span><span class="sxs-lookup"><span data-stu-id="869a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="869a3-107">GetCachedInterfacePointers メソッド</span><span class="sxs-lookup"><span data-stu-id="869a3-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="869a3-108">現在、RCW でキャッシュされた生のインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="869a3-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="869a3-109">GetCachedInterfaceTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="869a3-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="869a3-110">現在のオブジェクトに大文字と小文字を区別またはとして使用されることは、列挙子インターフェイス型を提供します。</span><span class="sxs-lookup"><span data-stu-id="869a3-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="869a3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="869a3-111">Remarks</span></span>  
 <span data-ttu-id="869a3-112">デバッガーには、"ICorDebugValue"インターフェイスのインスタンスが、RCW を表すかどうかを確認する`QueryInterface`上で"ICorDebugValue"`IID_ICorDebugComObjectValue`します。</span><span class="sxs-lookup"><span data-stu-id="869a3-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="869a3-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="869a3-113">Requirements</span></span>  
 <span data-ttu-id="869a3-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="869a3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="869a3-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="869a3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="869a3-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="869a3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="869a3-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="869a3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869a3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="869a3-118">See also</span></span>

- [<span data-ttu-id="869a3-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="869a3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="869a3-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="869a3-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
