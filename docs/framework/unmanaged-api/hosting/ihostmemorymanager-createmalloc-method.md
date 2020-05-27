---
title: IHostMemoryManager::CreateMAlloc メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 89c1d7b043d4369bf16a851924711c3c9d75791e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804529"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="a3d83-102">IHostMemoryManager::CreateMAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="a3d83-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="a3d83-103">ホストによって作成されたヒープから割り当て要求を行うために使用される[IHostMAlloc](ihostmalloc-interface.md)インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a3d83-103">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d83-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3d83-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d83-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3d83-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="a3d83-106">から割り当てられるメモリの特性を指定する[MALLOC_TYPE](malloc-type-enumeration.md)フラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="a3d83-106">[in] A combination of [MALLOC_TYPE](malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="a3d83-107">入出力`IHostMAlloc`ホストによって提供されるインスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a3d83-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3d83-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a3d83-108">Return Value</span></span>  
  
|<span data-ttu-id="a3d83-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3d83-109">HRESULT</span></span>|<span data-ttu-id="a3d83-110">説明</span><span class="sxs-lookup"><span data-stu-id="a3d83-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3d83-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3d83-111">S_OK</span></span>|<span data-ttu-id="a3d83-112">`CreateMAlloc`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="a3d83-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="a3d83-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3d83-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3d83-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="a3d83-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3d83-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3d83-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3d83-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a3d83-116">The call timed out.</span></span>|  
|<span data-ttu-id="a3d83-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3d83-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3d83-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a3d83-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3d83-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3d83-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3d83-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="a3d83-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3d83-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3d83-121">E_FAIL</span></span>|<span data-ttu-id="a3d83-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a3d83-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3d83-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a3d83-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3d83-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a3d83-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a3d83-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a3d83-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a3d83-126">割り当て要求を完了するために必要な物理メモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="a3d83-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3d83-127">解説</span><span class="sxs-lookup"><span data-stu-id="a3d83-127">Remarks</span></span>  
 <span data-ttu-id="a3d83-128">`CreateMAlloc`CLR が標準の Win32 関数を使用する代わりに、ホストを通じて割り当て要求を行うことができるようにするオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a3d83-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d83-129">要件</span><span class="sxs-lookup"><span data-stu-id="a3d83-129">Requirements</span></span>  
 <span data-ttu-id="a3d83-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3d83-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d83-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a3d83-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3d83-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a3d83-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3d83-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3d83-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d83-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3d83-134">See also</span></span>

- [<span data-ttu-id="a3d83-135">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3d83-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="a3d83-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3d83-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
