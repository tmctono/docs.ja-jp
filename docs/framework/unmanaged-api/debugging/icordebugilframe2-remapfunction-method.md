---
title: ICorDebugILFrame2::RemapFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92885d2a6514839a864d6a345dd8af8b07b90c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489814"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="a2965-102">ICorDebugILFrame2::RemapFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="a2965-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="a2965-103">新しい Microsoft intermediate language (MSIL) オフセットを指定することで編集された関数を再マップします。</span><span class="sxs-lookup"><span data-stu-id="a2965-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2965-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2965-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2965-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2965-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="a2965-106">[in]スタック フレームの新しい MSIL オフセット命令ポインターを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2965-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="a2965-107">この値は、シーケンス ポイントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2965-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="a2965-108">この値の有効性を確保する、呼び出し元の責任になります。</span><span class="sxs-lookup"><span data-stu-id="a2965-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="a2965-109">など、MSIL のオフセットは関数の境界の外側では無効です。</span><span class="sxs-lookup"><span data-stu-id="a2965-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2965-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2965-110">Remarks</span></span>  
 <span data-ttu-id="a2965-111">フレームの関数が編集されている場合、デバッガーを呼び出して、`RemapFunction`フレームの関数の最新バージョンにスワップして実行できるようにするメソッド。</span><span class="sxs-lookup"><span data-stu-id="a2965-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="a2965-112">指定の MSIL オフセット、コードの実行が開始されます。</span><span class="sxs-lookup"><span data-stu-id="a2965-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2965-113">呼び出す`RemapFunction`と同様に、呼び出す[icordebugilframe::setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)、すぐにスレッドのスタック トレースの生成に関連するすべてのデバッグのインターフェイスを無効になります。</span><span class="sxs-lookup"><span data-stu-id="a2965-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="a2965-114">これらのインターフェイスを含める[ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)ICorDebugILFrame、ICorDebugInternalFrame、および ICorDebugNativeFrame します。</span><span class="sxs-lookup"><span data-stu-id="a2965-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="a2965-115">`RemapFunction`メソッドは、現在のフレームのコンテキストでのみと、次の場合のいずれかでのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a2965-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
-   <span data-ttu-id="a2965-116">受領後、 [icordebugmanagedcallback 2::functionremapopportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)続行されていないコールバック。</span><span class="sxs-lookup"><span data-stu-id="a2965-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
-   <span data-ttu-id="a2965-117">コードの実行のための停止中に、 [icordebugmanagedcallback::editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)このフレームのイベント。</span><span class="sxs-lookup"><span data-stu-id="a2965-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2965-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2965-118">Requirements</span></span>  
 <span data-ttu-id="a2965-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2965-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2965-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2965-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2965-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2965-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2965-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2965-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
