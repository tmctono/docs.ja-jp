---
title: IHostAssemblyManager::GetAssemblyStore メソッド
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62965fa928522052b6885769e02c0211ca8d3fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937941"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="53da8-102">IHostAssemblyManager::GetAssemblyStore メソッド</span><span class="sxs-lookup"><span data-stu-id="53da8-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="53da8-103">ホストによって読み込まれたアセンブリの一覧を表す[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="53da8-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53da8-104">構文</span><span class="sxs-lookup"><span data-stu-id="53da8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53da8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53da8-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="53da8-106">入出力`IHostAssemblyStore`インスタンスへの関数ポインター。ホストがを実装`IHostAssemblyStore`していない場合は null。</span><span class="sxs-lookup"><span data-stu-id="53da8-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53da8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="53da8-107">Return Value</span></span>  
  
|<span data-ttu-id="53da8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53da8-108">HRESULT</span></span>|<span data-ttu-id="53da8-109">説明</span><span class="sxs-lookup"><span data-stu-id="53da8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53da8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53da8-110">S_OK</span></span>|<span data-ttu-id="53da8-111">`GetAssemblyStore`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="53da8-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="53da8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53da8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53da8-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="53da8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53da8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53da8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53da8-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="53da8-115">The call timed out.</span></span>|  
|<span data-ttu-id="53da8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53da8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53da8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="53da8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53da8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53da8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53da8-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="53da8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53da8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53da8-120">E_FAIL</span></span>|<span data-ttu-id="53da8-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="53da8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53da8-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="53da8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53da8-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="53da8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="53da8-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="53da8-124">E_NOINTERFACE</span></span>|<span data-ttu-id="53da8-125">ホストはの`IHostAssemblyStore`実装を提供していません。</span><span class="sxs-lookup"><span data-stu-id="53da8-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53da8-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="53da8-126">Remarks</span></span>  
 <span data-ttu-id="53da8-127">`IHostAssemblyStore`ホストが CLR とは無関係にアセンブリおよびモジュールにバインドできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="53da8-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="53da8-128">通常、ホストはアセンブリストアを提供して、アセンブリをファイルシステム以外の形式から読み込むことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="53da8-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53da8-129">ホストがを実装`IHostAssemblyStore`していない場合、 `GetAssemblyStore`は HRESULT 値 E_NOINTERFACE を返し、を`ppAssemblyStore` null に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53da8-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53da8-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="53da8-130">Requirements</span></span>  
 <span data-ttu-id="53da8-131">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53da8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53da8-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="53da8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53da8-133">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="53da8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53da8-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53da8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53da8-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="53da8-135">See also</span></span>

- [<span data-ttu-id="53da8-136">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53da8-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="53da8-137">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53da8-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
