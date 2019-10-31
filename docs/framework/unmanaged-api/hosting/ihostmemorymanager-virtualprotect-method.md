---
title: IHostMemoryManager::VirtualProtect メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
ms.openlocfilehash: d39ad45e143026f40ffcf1339e923837f9e812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195859"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="f0f11-102">IHostMemoryManager::VirtualProtect メソッド</span><span class="sxs-lookup"><span data-stu-id="f0f11-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="f0f11-103">対応する Win32 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f0f11-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="f0f11-104">`VirtualProtect` の Win32 実装では、呼び出し元プロセスの仮想アドレス空間でコミットされたページの領域の保護が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f0f11-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f11-105">構文</span><span class="sxs-lookup"><span data-stu-id="f0f11-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0f11-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0f11-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="f0f11-107">から保護属性が変更される仮想メモリのベースアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0f11-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="f0f11-108">から変更するメモリページの領域のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="f0f11-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="f0f11-109">から適用するメモリ保護の種類。</span><span class="sxs-lookup"><span data-stu-id="f0f11-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="f0f11-110">入出力以前のメモリ保護値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0f11-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0f11-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="f0f11-111">Return Value</span></span>  
  
|<span data-ttu-id="f0f11-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0f11-112">HRESULT</span></span>|<span data-ttu-id="f0f11-113">説明</span><span class="sxs-lookup"><span data-stu-id="f0f11-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0f11-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0f11-114">S_OK</span></span>|<span data-ttu-id="f0f11-115">`VirtualProtect` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f0f11-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="f0f11-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0f11-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0f11-117">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f0f11-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0f11-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0f11-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0f11-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f0f11-119">The call timed out.</span></span>|  
|<span data-ttu-id="f0f11-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0f11-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0f11-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f0f11-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0f11-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0f11-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0f11-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f0f11-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0f11-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0f11-124">E_FAIL</span></span>|<span data-ttu-id="f0f11-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f0f11-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0f11-126">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f0f11-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0f11-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f0f11-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0f11-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0f11-128">Remarks</span></span>  
 <span data-ttu-id="f0f11-129">この `VirtualProtect` の実装は HRESULT 値を返しますが、Win32 実装は成功を示す0以外の値を返し、エラーを示す0の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f0f11-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="f0f11-130">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0f11-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f11-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="f0f11-131">Requirements</span></span>  
 <span data-ttu-id="f0f11-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0f11-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f11-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0f11-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0f11-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f0f11-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0f11-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f11-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f11-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0f11-136">See also</span></span>

- [<span data-ttu-id="f0f11-137">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0f11-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
