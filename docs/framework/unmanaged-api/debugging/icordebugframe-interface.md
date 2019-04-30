---
title: ICorDebugFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a15d7f16676b8b9d66f8d1ba7484f3fec5735a44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988755"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="69410-102">ICorDebugFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69410-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="69410-103">現在のスタックのフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="69410-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69410-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-104">Methods</span></span>  
  
|<span data-ttu-id="69410-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-105">Method</span></span>|<span data-ttu-id="69410-106">説明</span><span class="sxs-lookup"><span data-stu-id="69410-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69410-107">CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="69410-108">この基準としたステップ実行操作を実行する、ICorDebugStepper を取得します。`ICorDebugFrame`します。</span><span class="sxs-lookup"><span data-stu-id="69410-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="69410-109">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="69410-110">ポインターを取得、`ICorDebugFrame`このフレームで呼び出されると、この場合は null を返しますが、チェーン内の最も内側のフレームには、現在のチェーンでします。</span><span class="sxs-lookup"><span data-stu-id="69410-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="69410-111">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="69410-112">ポインターを取得、`ICorDebugFrame`というがこのフレームでは、現在のチェーン内か、この場合は null を返しますが、チェーン内の最も外側のフレーム。</span><span class="sxs-lookup"><span data-stu-id="69410-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="69410-113">GetChain メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="69410-114">この、ICorDebugChain へのポインターを取得します。`ICorDebugFrame`の一部です。</span><span class="sxs-lookup"><span data-stu-id="69410-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="69410-115">GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="69410-116">このスタック フレームに関連付けられている ICorDebugCode にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="69410-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="69410-117">GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="69410-118">このスタック フレームに関連付けられているコードを含む ICorDebugFunction にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="69410-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="69410-119">GetFunctionToken メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="69410-120">このスタック フレームに関連付けられているコードを含む関数のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="69410-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="69410-121">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="69410-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="69410-122">これによって表されるスタック フレームの絶対アドレス範囲を取得`ICorDebugFrame`します。</span><span class="sxs-lookup"><span data-stu-id="69410-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69410-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="69410-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69410-124">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="69410-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69410-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="69410-125">Requirements</span></span>  
 <span data-ttu-id="69410-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69410-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69410-127">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69410-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69410-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69410-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69410-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69410-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69410-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="69410-130">See also</span></span>

- [<span data-ttu-id="69410-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69410-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
