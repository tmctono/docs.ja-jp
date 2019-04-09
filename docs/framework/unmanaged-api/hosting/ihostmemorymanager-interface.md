---
title: IHostMemoryManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137359"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="cb2e7-102">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb2e7-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="cb2e7-103">Win32 仮想メモリの標準の関数を使用する代わりに、共通言語ランタイム (CLR) を通じて、ホストの仮想メモリの要求を行うことができるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb2e7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-104">Methods</span></span>  
  
|<span data-ttu-id="cb2e7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-105">Method</span></span>|<span data-ttu-id="cb2e7-106">説明</span><span class="sxs-lookup"><span data-stu-id="cb2e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb2e7-107">AcquiredVirtualAddressSpace メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="cb2e7-108">共通言語ランタイム (CLR) が、オペレーティング システムから指定されたメモリが獲得されるホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="cb2e7-109">CreateMAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="cb2e7-110">インターフェイス ポインターを取得、 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)ホストによって作成されたヒープからメモリの割り当てを要求するために使用するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="cb2e7-111">GetMemoryLoad メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="cb2e7-112">ホストによって報告された、現在使用されている物理メモリの量を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="cb2e7-113">NeedsVirtualAddressSpace メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="cb2e7-114">CLR が指定されたメモリを使用しようとしています。 しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="cb2e7-115">RegisterMemoryNotificationCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="cb2e7-116">ホストが、コンピューター上の現在のメモリ負荷の CLR に通知するために呼び出すコールバック関数へのポインターを登録します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="cb2e7-117">ReleasedVirtualAddressSpace メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="cb2e7-118">指定されたメモリを使用して、CLR が完了したことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="cb2e7-119">VirtualAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="cb2e7-120">予約またはコミットの呼び出し元のプロセス仮想アドレス空間内のページの領域、対応する Win32 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="cb2e7-121">VirtualFree メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="cb2e7-122">対応する Win32 関数の解放、デコミット、または解放され、呼び出し元のプロセス仮想アドレス空間内のページの領域をデコミットの論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="cb2e7-123">VirtualProtect メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="cb2e7-124">対応する Win32 関数の呼び出し元のプロセス仮想アドレス空間内のコミットされたページの領域で、保護を変更する論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="cb2e7-125">VirtualQuery メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2e7-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="cb2e7-126">対応する Win32 関数の呼び出し元のプロセス仮想アドレス空間内のページの範囲に関する情報を取得する論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb2e7-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb2e7-127">Remarks</span></span>  
 `IHostMemoryManager` <span data-ttu-id="cb2e7-128">また CLR ホストによって報告されたヒープのメモリ要求を行うと、プロセスのメモリ不足のレベルを取得するためのポインターを取得するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-128">also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb2e7-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb2e7-129">Requirements</span></span>  
 <span data-ttu-id="cb2e7-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb2e7-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb2e7-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb2e7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb2e7-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cb2e7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cb2e7-133">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cb2e7-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb2e7-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb2e7-134">See also</span></span>

- [<span data-ttu-id="cb2e7-135">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb2e7-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="cb2e7-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb2e7-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
