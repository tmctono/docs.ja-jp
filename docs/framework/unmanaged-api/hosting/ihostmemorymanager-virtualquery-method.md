---
title: IHostMemoryManager::VirtualQuery メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
ms.openlocfilehash: 00ec0b92a9f7151ee9b831c85548c4f61d87af68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192031"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="82a60-102">IHostMemoryManager::VirtualQuery メソッド</span><span class="sxs-lookup"><span data-stu-id="82a60-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="82a60-103">対応する Win32 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="82a60-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="82a60-104">`VirtualQuery` の Win32 実装では、呼び出し元プロセスの仮想アドレス空間にあるページの範囲に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="82a60-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a60-105">構文</span><span class="sxs-lookup"><span data-stu-id="82a60-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82a60-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82a60-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="82a60-107">から照会される仮想メモリ内のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="82a60-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="82a60-108">入出力指定されたメモリ領域に関する情報を格納している構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="82a60-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="82a60-109">から`lpBuffer` が指すバッファーのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="82a60-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="82a60-110">入出力情報バッファーによって返されたバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="82a60-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82a60-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="82a60-111">Return Value</span></span>  
  
|<span data-ttu-id="82a60-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82a60-112">HRESULT</span></span>|<span data-ttu-id="82a60-113">説明</span><span class="sxs-lookup"><span data-stu-id="82a60-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82a60-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="82a60-114">S_OK</span></span>|<span data-ttu-id="82a60-115">`VirtualQuery` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="82a60-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="82a60-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82a60-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82a60-117">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="82a60-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82a60-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82a60-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82a60-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="82a60-119">The call timed out.</span></span>|  
|<span data-ttu-id="82a60-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82a60-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82a60-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="82a60-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82a60-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82a60-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82a60-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="82a60-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82a60-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82a60-124">E_FAIL</span></span>|<span data-ttu-id="82a60-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="82a60-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82a60-126">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="82a60-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82a60-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="82a60-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a60-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="82a60-128">Remarks</span></span>  
 <span data-ttu-id="82a60-129">`VirtualQuery` は、呼び出し元プロセスの仮想アドレス空間にあるページの範囲に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="82a60-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="82a60-130">この実装では、`pResult` パラメーターの値を、情報バッファーで返されるバイト数に設定し、HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="82a60-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="82a60-131">Win32 `VirtualQuery` 関数では、戻り値はバッファーサイズです。</span><span class="sxs-lookup"><span data-stu-id="82a60-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="82a60-132">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82a60-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="82a60-133">オペレーティングシステムの `VirtualQuery` の実装では、デッドロックは発生せず、ユーザーコード内で中断されたランダムなスレッドで完了まで実行できます。</span><span class="sxs-lookup"><span data-stu-id="82a60-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="82a60-134">このメソッドのホストされたバージョンを実装する場合は、細心の注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="82a60-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a60-135">［要件］</span><span class="sxs-lookup"><span data-stu-id="82a60-135">Requirements</span></span>  
 <span data-ttu-id="82a60-136">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82a60-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a60-137">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="82a60-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82a60-138">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="82a60-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82a60-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82a60-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a60-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="82a60-140">See also</span></span>

- [<span data-ttu-id="82a60-141">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82a60-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
