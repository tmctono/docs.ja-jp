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
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936999"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="205ae-102">ICorDebugFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="205ae-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="205ae-103">現在のスタックのフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="205ae-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="205ae-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-104">Methods</span></span>  
  
|<span data-ttu-id="205ae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-105">Method</span></span>|<span data-ttu-id="205ae-106">説明</span><span class="sxs-lookup"><span data-stu-id="205ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="205ae-107">CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="205ae-108">この`ICorDebugFrame`に対して相対的なステップ実行操作を実行する ICorDebugStepper を取得します。</span><span class="sxs-lookup"><span data-stu-id="205ae-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="205ae-109">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="205ae-110">このフレームが呼び出され`ICorDebugFrame`た現在のチェーン内のへのポインターを取得します。または、このがチェーン内の最も内側のフレームである場合は null を返します。</span><span class="sxs-lookup"><span data-stu-id="205ae-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="205ae-111">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="205ae-112">このフレームを呼び出した`ICorDebugFrame`現在のチェーン内のへのポインターを取得します。これがチェーンの最も外側のフレームである場合は null を返します。</span><span class="sxs-lookup"><span data-stu-id="205ae-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="205ae-113">GetChain メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="205ae-114">この`ICorDebugFrame`が含まれている、ツールチェーンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="205ae-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="205ae-115">GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="205ae-116">このスタックフレームに関連付けられているテキストコードへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="205ae-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="205ae-117">GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="205ae-118">このスタックフレームに関連付けられているコードを格納しているコードを指すポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="205ae-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="205ae-119">GetFunctionToken メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="205ae-120">このスタックフレームに関連付けられているコードを含む関数のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="205ae-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="205ae-121">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="205ae-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="205ae-122">この`ICorDebugFrame`によって表されるスタックフレームの絶対アドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="205ae-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="205ae-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="205ae-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="205ae-124">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="205ae-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="205ae-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="205ae-125">Requirements</span></span>  
 <span data-ttu-id="205ae-126">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="205ae-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="205ae-127">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="205ae-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="205ae-128">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="205ae-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="205ae-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="205ae-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205ae-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="205ae-130">See also</span></span>

- [<span data-ttu-id="205ae-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="205ae-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
