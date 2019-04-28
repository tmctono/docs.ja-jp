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
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700827"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="2b032-102">ICorDebugHeapValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b032-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="2b032-103">共通言語ランタイム (CLR) のガベージ コレクターによって収集されたオブジェクトを表す"ICorDebugValue"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="2b032-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b032-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2b032-104">Methods</span></span>  
  
|<span data-ttu-id="2b032-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2b032-105">Method</span></span>|<span data-ttu-id="2b032-106">説明</span><span class="sxs-lookup"><span data-stu-id="2b032-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b032-107">CreateRelocBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="2b032-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="2b032-108">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="2b032-108">Not implemented.</span></span>|  
|[<span data-ttu-id="2b032-109">IsValid メソッド</span><span class="sxs-lookup"><span data-stu-id="2b032-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="2b032-110">オブジェクトが、これによって表されるかどうかを示す値を取得します`ICorDebugHeapValue`有効ですが、またはガベージ コレクターによって解放されています。</span><span class="sxs-lookup"><span data-stu-id="2b032-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="2b032-111">このメソッドは、.NET Framework version 2.0 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="2b032-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b032-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b032-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b032-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2b032-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b032-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b032-114">Requirements</span></span>  
 <span data-ttu-id="2b032-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b032-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b032-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b032-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b032-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b032-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b032-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b032-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b032-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b032-119">See also</span></span>

- [<span data-ttu-id="2b032-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b032-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
