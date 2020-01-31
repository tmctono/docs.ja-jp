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
ms.openlocfilehash: fa31b8a6cc96935319e9bef3e561790b65e33a87
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777587"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="e6631-102">ICorDebugHeapValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6631-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="e6631-103">共通言語ランタイム (CLR) ガベージコレクターによって収集されたオブジェクトを表す "ICorDebugValue" のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="e6631-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6631-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e6631-104">Methods</span></span>  
  
|<span data-ttu-id="e6631-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e6631-105">Method</span></span>|<span data-ttu-id="e6631-106">説明</span><span class="sxs-lookup"><span data-stu-id="e6631-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6631-107">CreateRelocBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="e6631-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="e6631-108">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="e6631-108">Not implemented.</span></span>|  
|[<span data-ttu-id="e6631-109">IsValid メソッド</span><span class="sxs-lookup"><span data-stu-id="e6631-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="e6631-110">この `ICorDebugHeapValue` によって表されるオブジェクトが有効かどうか、またはガベージコレクターによって回収されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6631-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="e6631-111">このメソッドは .NET Framework バージョン2.0 では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="e6631-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6631-112">コメント</span><span class="sxs-lookup"><span data-stu-id="e6631-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6631-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e6631-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6631-114">要件</span><span class="sxs-lookup"><span data-stu-id="e6631-114">Requirements</span></span>  
 <span data-ttu-id="e6631-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6631-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6631-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6631-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6631-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6631-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6631-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6631-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6631-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6631-119">See also</span></span>

- [<span data-ttu-id="e6631-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6631-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
