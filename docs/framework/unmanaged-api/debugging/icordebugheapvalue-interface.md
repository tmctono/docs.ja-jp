---
title: ICorDebugHeapValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 4f87065fc4a3d80a8363f3ae2fbb76c29f3d9b96
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138413"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="fca83-102">ICorDebugHeapValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fca83-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="fca83-103">共通言語ランタイム (CLR) ガベージコレクターによって収集されたオブジェクトを表す "ICorDebugValue" のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="fca83-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fca83-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fca83-104">Methods</span></span>  
  
|<span data-ttu-id="fca83-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fca83-105">Method</span></span>|<span data-ttu-id="fca83-106">説明</span><span class="sxs-lookup"><span data-stu-id="fca83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fca83-107">CreateRelocBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="fca83-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="fca83-108">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="fca83-108">Not implemented.</span></span>|  
|[<span data-ttu-id="fca83-109">IsValid メソッド</span><span class="sxs-lookup"><span data-stu-id="fca83-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="fca83-110">この `ICorDebugHeapValue` によって表されるオブジェクトが有効かどうか、またはガベージコレクターによって回収されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fca83-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="fca83-111">このメソッドは .NET Framework バージョン2.0 では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="fca83-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fca83-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="fca83-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fca83-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fca83-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fca83-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="fca83-114">Requirements</span></span>  
 <span data-ttu-id="fca83-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fca83-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fca83-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fca83-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fca83-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fca83-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fca83-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fca83-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca83-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fca83-119">See also</span></span>

- [<span data-ttu-id="fca83-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fca83-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
