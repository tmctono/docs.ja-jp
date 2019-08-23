---
title: ICorDebug インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afbf480d69e97662b5963706bb8c192aec0325a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966290"
---
# <a name="icordebug-interface"></a><span data-ttu-id="8ccdd-102">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ccdd-102">ICorDebug Interface</span></span>
<span data-ttu-id="8ccdd-103">開発者が共通言語ランタイム (CLR) 環境でアプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ccdd-104">混合モード (マネージコードとネイティブコード) のデバッグは、Windows 95、Windows 98、または Windows ME ではサポートされておらず、x86 以外のプラットフォーム (IA64 や AMD64 など) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ccdd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-105">Methods</span></span>  
  
|<span data-ttu-id="8ccdd-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-106">Method</span></span>|<span data-ttu-id="8ccdd-107">説明</span><span class="sxs-lookup"><span data-stu-id="8ccdd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ccdd-108">CanLaunchOrAttach メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="8ccdd-109">現在のコンピューターおよびランタイム構成のコンテキスト内で、新しいプロセスを起動するか、指定したプロセスにアタッチするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="8ccdd-110">CreateProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="8ccdd-111">デバッガーの制御下でプロセスとそのプライマリスレッドを起動します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="8ccdd-112">DebugActiveProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="8ccdd-113">デバッガーを既存のプロセスにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="8ccdd-114">EnumerateProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="8ccdd-115">デバッグ中のプロセスの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="8ccdd-116">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="8ccdd-117">指定されたプロセス ID を持つ "いいプロセス" オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="8ccdd-118">Initialize メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="8ccdd-119">`ICorDebug` オブジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="8ccdd-120">SetManagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="8ccdd-121">マネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="8ccdd-122">SetUnmanagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="8ccdd-123">アンマネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="8ccdd-124">Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="8ccdd-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="8ccdd-125">オブジェクトを`ICorDebug`終了します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ccdd-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ccdd-126">Remarks</span></span>  
 <span data-ttu-id="8ccdd-127">`ICorDebug`デバッガープロセスのイベント処理ループを表します。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="8ccdd-128">デバッガーは、このインターフェイスを解放する前に、デバッグされているすべてのプロセスからの "ExitProcess" コール[バック](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)を待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="8ccdd-129">`ICorDebug`オブジェクトは、さらに管理されているすべてのデバッグを制御するための初期オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="8ccdd-130">.NET Framework バージョン1.0 および1.1 では、このオブジェクトは COM `CoClass`から作成されたオブジェクトでした。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="8ccdd-131">.NET Framework バージョン2.0 では、このオブジェクトは`CoClass`オブジェクトではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="8ccdd-132">これは、バージョンを認識する[CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)関数によって作成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="8ccdd-133">この新しい作成関数を使用すると、クライアントは特定`ICorDebug`のバージョンのデバッグ API もエミュレートするの特定の実装を取得できます。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ccdd-134">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ccdd-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ccdd-135">Requirements</span></span>  
 <span data-ttu-id="8ccdd-136">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ccdd-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ccdd-137">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8ccdd-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ccdd-138">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="8ccdd-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ccdd-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ccdd-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ccdd-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ccdd-140">See also</span></span>

- [<span data-ttu-id="8ccdd-141">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ccdd-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
