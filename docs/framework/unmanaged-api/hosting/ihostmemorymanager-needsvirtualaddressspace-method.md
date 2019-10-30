---
title: IHostMemoryManager::NeedsVirtualAddressSpace メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
ms.openlocfilehash: a3ae474a73f4c8e4b98c4b2bc5d04e55bcae6874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128664"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="84838-102">IHostMemoryManager::NeedsVirtualAddressSpace メソッド</span><span class="sxs-lookup"><span data-stu-id="84838-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="84838-103">共通言語ランタイム (CLR) が、指定されたメモリを使用しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="84838-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84838-104">構文</span><span class="sxs-lookup"><span data-stu-id="84838-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84838-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84838-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="84838-106">からメモリの開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="84838-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="84838-107">からメモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="84838-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84838-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="84838-108">Remarks</span></span>  
 <span data-ttu-id="84838-109">`NeedsVirtualAddressSpace` メソッドはコールバックメソッドであり、ホストアプリケーションのライターによって実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="84838-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="84838-110">これは CLR によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="84838-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="84838-111">ホストが、指定されたメモリを使用しないようにする場合は、E_OUTOFMEMORY HRESULT を返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="84838-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84838-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="84838-112">Requirements</span></span>  
 <span data-ttu-id="84838-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84838-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84838-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="84838-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84838-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="84838-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84838-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84838-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84838-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="84838-117">See also</span></span>

- [<span data-ttu-id="84838-118">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84838-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
