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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222569"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="9f6f5-102">ICorDebugFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f6f5-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="9f6f5-103">現在のスタックのフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9f6f5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-104">Methods</span></span>  
  
|<span data-ttu-id="9f6f5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-105">Method</span></span>|<span data-ttu-id="9f6f5-106">説明</span><span class="sxs-lookup"><span data-stu-id="9f6f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9f6f5-107">CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="9f6f5-108">この基準としたステップ実行操作を実行する、ICorDebugStepper を取得します。`ICorDebugFrame`します。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="9f6f5-109">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="9f6f5-110">ポインターを取得、`ICorDebugFrame`このフレームで呼び出されると、この場合は null を返しますが、チェーン内の最も内側のフレームには、現在のチェーンでします。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="9f6f5-111">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="9f6f5-112">ポインターを取得、`ICorDebugFrame`というがこのフレームでは、現在のチェーン内か、この場合は null を返しますが、チェーン内の最も外側のフレーム。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="9f6f5-113">GetChain メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="9f6f5-114">この、ICorDebugChain へのポインターを取得します。`ICorDebugFrame`の一部です。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="9f6f5-115">GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="9f6f5-116">このスタック フレームに関連付けられている ICorDebugCode にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="9f6f5-117">GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="9f6f5-118">このスタック フレームに関連付けられているコードを含む ICorDebugFunction にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="9f6f5-119">GetFunctionToken メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="9f6f5-120">このスタック フレームに関連付けられているコードを含む関数のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="9f6f5-121">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="9f6f5-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="9f6f5-122">これによって表されるスタック フレームの絶対アドレス範囲を取得`ICorDebugFrame`します。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f6f5-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f6f5-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f6f5-124">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f6f5-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f6f5-125">Requirements</span></span>  
 <span data-ttu-id="9f6f5-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f6f5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f6f5-127">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f6f5-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f6f5-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f6f5-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f6f5-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f6f5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6f5-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f6f5-130">See also</span></span>

- [<span data-ttu-id="9f6f5-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f6f5-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
