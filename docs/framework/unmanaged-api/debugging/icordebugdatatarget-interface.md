---
title: ICorDebugDataTarget インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
ms.openlocfilehash: 9029d53872108bc1953fd22c584b6e01a6f3c7ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788863"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="ff825-102">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff825-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="ff825-103">特定のターゲット プロセスにアクセスするためのコールバック インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ff825-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff825-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff825-104">Methods</span></span>  
  
|<span data-ttu-id="ff825-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff825-105">Method</span></span>|<span data-ttu-id="ff825-106">説明</span><span class="sxs-lookup"><span data-stu-id="ff825-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff825-107">GetPlatform メソッド</span><span class="sxs-lookup"><span data-stu-id="ff825-107">GetPlatform Method</span></span>](icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="ff825-108">ターゲットプロセスが実行されているプラットフォーム (プロセッサアーキテクチャやオペレーティングシステムなど) に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff825-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="ff825-109">ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="ff825-109">ReadVirtual Method</span></span>](icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="ff825-110">指定したアドレスを開始位置として連続したメモリのブロックを取得し、指定したバッファー内でそれを返します。</span><span class="sxs-lookup"><span data-stu-id="ff825-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="ff825-111">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="ff825-111">GetThreadContext Method</span></span>](icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="ff825-112">指定されたスレッドの現在のスレッドコンテキストを要求します。</span><span class="sxs-lookup"><span data-stu-id="ff825-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff825-113">コメント</span><span class="sxs-lookup"><span data-stu-id="ff825-113">Remarks</span></span>  
 <span data-ttu-id="ff825-114">`ICorDebugDataTarget` とそのメソッドには、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="ff825-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="ff825-115">デバッグサービスは、このインターフェイスのメソッドを呼び出して、ターゲットプロセス内のメモリおよびその他のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ff825-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="ff825-116">デバッガークライアントは、特定のターゲット (ライブプロセスやメモリダンプなど) に適した方法でこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff825-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="ff825-117">`ICorDebugDataTarget` メソッドは、他の `ICorDebug*` インターフェイスに実装されているメソッド内からのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ff825-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="ff825-118">これにより、デバッガークライアントは、呼び出されるスレッドとそのタイミングを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ff825-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="ff825-119">`ICorDebugDataTarget` の実装は、常にターゲットに関する最新の情報を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff825-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="ff825-120">`ICorDebug*` インターフェイス (および `ICorDebugDataTarget` メソッド) が呼び出されている間は、ターゲットプロセスを停止し、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff825-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="ff825-121">ターゲットがライブプロセスであり、その状態が変更された場合、 [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)メソッドを再度呼び出して、置換されたののインスタンスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff825-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff825-122">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ff825-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff825-123">要件</span><span class="sxs-lookup"><span data-stu-id="ff825-123">Requirements</span></span>  
 <span data-ttu-id="ff825-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff825-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff825-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff825-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff825-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff825-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff825-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff825-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff825-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff825-128">See also</span></span>

- [<span data-ttu-id="ff825-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff825-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ff825-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ff825-130">Debugging</span></span>](index.md)
