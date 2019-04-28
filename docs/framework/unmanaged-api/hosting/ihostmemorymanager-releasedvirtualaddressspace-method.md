---
title: IHostMemoryManager::ReleasedVirtualAddressSpace メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0acbf4163e98b1171510260c4fac72c3d6f6fb1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934850"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="f24fd-102">IHostMemoryManager::ReleasedVirtualAddressSpace メソッド</span><span class="sxs-lookup"><span data-stu-id="f24fd-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="f24fd-103">共通言語ランタイム (CLR) の指定されたメモリの使用が完了したことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="f24fd-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f24fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="f24fd-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f24fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f24fd-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="f24fd-106">[in]解放するメモリの開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f24fd-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f24fd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f24fd-107">Remarks</span></span>  
 <span data-ttu-id="f24fd-108">`ReleasedVirtualAddressSpace`メソッドは、コールバック メソッドであり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24fd-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="f24fd-109">CLR によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f24fd-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f24fd-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f24fd-110">Requirements</span></span>  
 <span data-ttu-id="f24fd-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f24fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f24fd-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f24fd-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f24fd-113">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f24fd-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f24fd-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f24fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24fd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f24fd-115">See also</span></span>

- [<span data-ttu-id="f24fd-116">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f24fd-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
