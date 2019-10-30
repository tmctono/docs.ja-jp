---
title: IHostAssemblyManager::GetNonHostStoreAssemblies メソッド
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
ms.openlocfilehash: eb715e1a4f9a210a1440874a9a8cea2d85345d33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124577"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="6c888-102">IHostAssemblyManager::GetNonHostStoreAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="6c888-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="6c888-103">ホストが読み込みのために共通言語ランタイム (CLR) を必要とするアセンブリのリストを表す[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c888-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c888-104">構文</span><span class="sxs-lookup"><span data-stu-id="6c888-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c888-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c888-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="6c888-106">入出力ホストが CLR の読み込みを想定しているアセンブリへの参照の一覧を含む `ICLRAssemblyReferenceList` のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c888-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c888-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6c888-107">Return Value</span></span>  
  
|<span data-ttu-id="6c888-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c888-108">HRESULT</span></span>|<span data-ttu-id="6c888-109">説明</span><span class="sxs-lookup"><span data-stu-id="6c888-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c888-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c888-110">S_OK</span></span>|<span data-ttu-id="6c888-111">`GetNonHostStoreAssemblies` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6c888-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="6c888-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c888-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c888-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="6c888-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c888-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c888-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c888-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="6c888-115">The call timed out.</span></span>|  
|<span data-ttu-id="6c888-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c888-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c888-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6c888-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c888-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c888-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c888-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="6c888-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c888-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c888-120">E_FAIL</span></span>|<span data-ttu-id="6c888-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6c888-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c888-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6c888-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c888-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6c888-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6c888-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6c888-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6c888-125">要求された `ICLRAssemblyReferenceList`の参照の一覧を作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="6c888-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c888-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c888-126">Remarks</span></span>  
 <span data-ttu-id="6c888-127">CLR は、次の一連のガイドラインを使用して参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="6c888-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="6c888-128">まず、`GetNonHostStoreAssemblies`によって返されるアセンブリ参照の一覧を参照します。</span><span class="sxs-lookup"><span data-stu-id="6c888-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="6c888-129">アセンブリが一覧に表示されている場合、CLR は通常どおりにバインドします。</span><span class="sxs-lookup"><span data-stu-id="6c888-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="6c888-130">アセンブリが一覧に表示されず、ホストが[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)の実装を提供した場合、CLR は[IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)を呼び出して、バインド先のアセンブリをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c888-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="6c888-131">それ以外の場合、CLR はアセンブリへのバインドに失敗します。</span><span class="sxs-lookup"><span data-stu-id="6c888-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="6c888-132">ホストが `ppReferenceList` を null に設定した場合、CLR はまずグローバルアセンブリキャッシュをプローブし、`ProvideAssembly`を呼び出します。次に、アプリケーションベースをプローブしてアセンブリ参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="6c888-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c888-133">初期化時に、CLR は `GetNonHostStoreAssemblies` を1回だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c888-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="6c888-134">メソッドが再度呼び出されていません。</span><span class="sxs-lookup"><span data-stu-id="6c888-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c888-135">［要件］</span><span class="sxs-lookup"><span data-stu-id="6c888-135">Requirements</span></span>  
 <span data-ttu-id="6c888-136">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c888-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c888-137">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6c888-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c888-138">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6c888-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c888-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c888-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c888-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c888-140">See also</span></span>

- [<span data-ttu-id="6c888-141">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c888-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="6c888-142">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c888-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="6c888-143">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c888-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
