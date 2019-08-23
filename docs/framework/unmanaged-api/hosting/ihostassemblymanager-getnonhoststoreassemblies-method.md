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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccd73963302ae99c7d5d1a7201bc77c4544363f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937895"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="deb49-102">IHostAssemblyManager::GetNonHostStoreAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="deb49-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="deb49-103">ホストが読み込みのために共通言語ランタイム (CLR) を必要とするアセンブリのリストを表す[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="deb49-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb49-104">構文</span><span class="sxs-lookup"><span data-stu-id="deb49-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb49-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="deb49-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="deb49-106">入出力ホストが CLR を読み込むことを`ICLRAssemblyReferenceList`想定しているアセンブリへの参照の一覧を含むのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="deb49-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="deb49-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="deb49-107">Return Value</span></span>  
  
|<span data-ttu-id="deb49-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="deb49-108">HRESULT</span></span>|<span data-ttu-id="deb49-109">説明</span><span class="sxs-lookup"><span data-stu-id="deb49-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="deb49-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="deb49-110">S_OK</span></span>|<span data-ttu-id="deb49-111">`GetNonHostStoreAssemblies`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="deb49-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="deb49-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="deb49-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="deb49-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="deb49-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="deb49-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="deb49-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="deb49-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="deb49-115">The call timed out.</span></span>|  
|<span data-ttu-id="deb49-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="deb49-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="deb49-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="deb49-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="deb49-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="deb49-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="deb49-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="deb49-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="deb49-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="deb49-120">E_FAIL</span></span>|<span data-ttu-id="deb49-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="deb49-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="deb49-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="deb49-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="deb49-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="deb49-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="deb49-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="deb49-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="deb49-125">要求さ`ICLRAssemblyReferenceList`れたの参照の一覧を作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="deb49-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="deb49-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="deb49-126">Remarks</span></span>  
 <span data-ttu-id="deb49-127">CLR は、次の一連のガイドラインを使用して参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="deb49-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="deb49-128">まず、によって`GetNonHostStoreAssemblies`返されるアセンブリ参照の一覧を参照します。</span><span class="sxs-lookup"><span data-stu-id="deb49-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="deb49-129">アセンブリが一覧に表示されている場合、CLR は通常どおりにバインドします。</span><span class="sxs-lookup"><span data-stu-id="deb49-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="deb49-130">アセンブリが一覧に表示されず、ホストが[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)の実装を提供した場合、CLR は[IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)を呼び出して、バインド先のアセンブリをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="deb49-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="deb49-131">それ以外の場合、CLR はアセンブリへのバインドに失敗します。</span><span class="sxs-lookup"><span data-stu-id="deb49-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="deb49-132">ホストが null に`ppReferenceList`設定されている場合、CLR はまずグローバルアセンブリキャッシュ`ProvideAssembly`をプローブし、を呼び出してから、アプリケーションベースをプローブしてアセンブリ参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="deb49-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="deb49-133">初期化時に、CLR は`GetNonHostStoreAssemblies` 1 回だけを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="deb49-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="deb49-134">メソッドが再度呼び出されていません。</span><span class="sxs-lookup"><span data-stu-id="deb49-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb49-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="deb49-135">Requirements</span></span>  
 <span data-ttu-id="deb49-136">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb49-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb49-137">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="deb49-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="deb49-138">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="deb49-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="deb49-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb49-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb49-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="deb49-140">See also</span></span>

- [<span data-ttu-id="deb49-141">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="deb49-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="deb49-142">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="deb49-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="deb49-143">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="deb49-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
