---
title: ICorDebugProcess2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 213eb86c36225a6194af83c04c469fbe0cc51b63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137146"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="44922-102">ICorDebugProcess2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44922-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="44922-103">は、マネージコードを実行しているプロセスを表す、のような、の論理拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="44922-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44922-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-104">Methods</span></span>  
  
|<span data-ttu-id="44922-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-105">Method</span></span>|<span data-ttu-id="44922-106">説明</span><span class="sxs-lookup"><span data-stu-id="44922-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44922-107">ClearUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="44922-108">`ICorDebugProcess2::SetUnmanagedBreakpoint`の以前の呼び出しによって設定された、指定したオフセットの位置にあるブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="44922-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="44922-109">GetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="44922-110">この `ICorDebugProcess2`によって参照されるプロセスにイメージを読み込むために共通言語ランタイム (CLR) に対して設定する必要があるフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="44922-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="44922-111">GetReferenceValueFromGCHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="44922-112">ガベージコレクションハンドルを持つ指定したマネージオブジェクトへの参照ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="44922-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="44922-113">GetThreadForTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="44922-114">指定した id を持つタスクが実行されているスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="44922-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="44922-115">GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="44922-116">デバッグ中のプロセスが実行されている CLR のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="44922-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="44922-117">SetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="44922-118">Just-in-time (JIT) コンパイラがデバッグ中のプロセスにイメージを読み込むために必要なフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="44922-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="44922-119">SetUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="44922-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="44922-120">指定したネイティブイメージオフセットにアンマネージブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="44922-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44922-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="44922-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44922-122">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="44922-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44922-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="44922-123">Requirements</span></span>  
 <span data-ttu-id="44922-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44922-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44922-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44922-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44922-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44922-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44922-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44922-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44922-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="44922-128">See also</span></span>

- [<span data-ttu-id="44922-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44922-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
