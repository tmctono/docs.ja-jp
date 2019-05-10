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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9a87ae4381ec5bc0d8c416ef4ee4c13b04a862f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606897"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="6e787-102">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e787-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="6e787-103">特定のターゲット プロセスにアクセスするためのコールバック インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6e787-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e787-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6e787-104">Methods</span></span>  
  
|<span data-ttu-id="6e787-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6e787-105">Method</span></span>|<span data-ttu-id="6e787-106">説明</span><span class="sxs-lookup"><span data-stu-id="6e787-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e787-107">GetPlatform メソッド</span><span class="sxs-lookup"><span data-stu-id="6e787-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="6e787-108">プロセッサ アーキテクチャと、ターゲット プロセスが実行されているオペレーティング システムを含む、プラットフォームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6e787-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="6e787-109">ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="6e787-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="6e787-110">指定したアドレスから始まる連続したメモリのブロックを取得し、指定されたバッファーで返します。</span><span class="sxs-lookup"><span data-stu-id="6e787-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="6e787-111">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="6e787-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="6e787-112">指定したスレッドの現在のスレッド コンテキストを要求します。</span><span class="sxs-lookup"><span data-stu-id="6e787-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e787-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e787-113">Remarks</span></span>  
 <span data-ttu-id="6e787-114">`ICorDebugDataTarget` そのメソッドに次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="6e787-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="6e787-115">デバッグ サービスは、メモリと、ターゲット プロセスの他のデータにアクセスするには、このインターフェイスでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6e787-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="6e787-116">デバッガー クライアントは、特定のターゲット (たとえば、ライブ プロセスまたはメモリ ダンプ) に適したには、このインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e787-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="6e787-117">`ICorDebugDataTarget`メソッドは、他の実装されているメソッド内からのみ呼び出すことが`ICorDebug*`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6e787-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="6e787-118">これにより、どのスレッドが呼び出されると、デバッガーのクライアントが制御すること。</span><span class="sxs-lookup"><span data-stu-id="6e787-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="6e787-119">`ICorDebugDataTarget`実装する必要があります、ターゲットに関する最新の情報を常に返します。</span><span class="sxs-lookup"><span data-stu-id="6e787-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="6e787-120">ターゲット プロセスを停止しているときに何らかの方法で変更されていない必要があります`ICorDebug*`インターフェイス (したがって`ICorDebugDataTarget`メソッド) が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6e787-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="6e787-121">ターゲットがライブ プロセスとその状態の変更の場合、 [iclrdebugging::openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)メソッドは、置換 ICorDebugProcess のインスタンスを指定してもう一度呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e787-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e787-122">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6e787-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e787-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e787-123">Requirements</span></span>  
 <span data-ttu-id="6e787-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e787-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e787-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e787-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e787-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e787-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e787-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e787-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e787-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e787-128">See also</span></span>

- [<span data-ttu-id="6e787-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e787-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6e787-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6e787-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
