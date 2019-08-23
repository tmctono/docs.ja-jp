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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb130f11975eb95db7807126d6f163425439b0c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914896"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="f2dfa-102">ICorDebugHeapValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2dfa-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="f2dfa-103">共通言語ランタイム (CLR) ガベージコレクターによって収集されたオブジェクトを表す "ICorDebugValue" のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2dfa-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f2dfa-104">Methods</span></span>  
  
|<span data-ttu-id="f2dfa-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f2dfa-105">Method</span></span>|<span data-ttu-id="f2dfa-106">説明</span><span class="sxs-lookup"><span data-stu-id="f2dfa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2dfa-107">CreateRelocBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="f2dfa-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="f2dfa-108">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-108">Not implemented.</span></span>|  
|[<span data-ttu-id="f2dfa-109">IsValid メソッド</span><span class="sxs-lookup"><span data-stu-id="f2dfa-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="f2dfa-110">この`ICorDebugHeapValue`によって表されるオブジェクトが有効かどうか、またはガベージコレクターによって解放されたかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="f2dfa-111">このメソッドは .NET Framework バージョン2.0 では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2dfa-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2dfa-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2dfa-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2dfa-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2dfa-114">Requirements</span></span>  
 <span data-ttu-id="f2dfa-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2dfa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2dfa-116">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f2dfa-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2dfa-117">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="f2dfa-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2dfa-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2dfa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2dfa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2dfa-119">See also</span></span>

- [<span data-ttu-id="f2dfa-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2dfa-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
