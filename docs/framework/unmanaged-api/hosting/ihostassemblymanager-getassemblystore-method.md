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
ms.openlocfilehash: 35e38949ce945d93216daffd3c0d91dad6c8739b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763192"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="f2358-102">IHostAssemblyManager::GetAssemblyStore メソッド</span><span class="sxs-lookup"><span data-stu-id="f2358-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="f2358-103">インターフェイス ポインターを取得、 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)ホストによって読み込まれたアセンブリの一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="f2358-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2358-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2358-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2358-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2358-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="f2358-106">[out]関数へのポインター、`IHostAssemblyStore`インスタンス、またはホストが実装していない場合は、null`IHostAssemblyStore`します。</span><span class="sxs-lookup"><span data-stu-id="f2358-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2358-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f2358-107">Return Value</span></span>  
  
|<span data-ttu-id="f2358-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2358-108">HRESULT</span></span>|<span data-ttu-id="f2358-109">説明</span><span class="sxs-lookup"><span data-stu-id="f2358-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2358-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2358-110">S_OK</span></span>|<span data-ttu-id="f2358-111">`GetAssemblyStore` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="f2358-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="f2358-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2358-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2358-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="f2358-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2358-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2358-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2358-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="f2358-115">The call timed out.</span></span>|  
|<span data-ttu-id="f2358-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2358-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2358-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f2358-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2358-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2358-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2358-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="f2358-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2358-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2358-120">E_FAIL</span></span>|<span data-ttu-id="f2358-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f2358-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2358-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2358-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2358-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2358-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f2358-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="f2358-124">E_NOINTERFACE</span></span>|<span data-ttu-id="f2358-125">ホストがの実装を提供しない`IHostAssemblyStore`します。</span><span class="sxs-lookup"><span data-stu-id="f2358-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2358-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2358-126">Remarks</span></span>  
 <span data-ttu-id="f2358-127">`IHostAssemblyStore` ホストがアセンブリと CLR とは無関係にモジュールにバインドできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2358-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="f2358-128">ホストは、通常、ファイル システム以外の形式から読み込まれるアセンブリを許可するアセンブリのストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2358-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2358-129">ホストが実装していない場合`IHostAssemblyStore`、 `GetAssemblyStore` E_NOINTERFACE の HRESULT 値を返す必要があり、設定する必要があります`ppAssemblyStore`を null にします。</span><span class="sxs-lookup"><span data-stu-id="f2358-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2358-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2358-130">Requirements</span></span>  
 <span data-ttu-id="f2358-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2358-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2358-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2358-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2358-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f2358-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2358-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2358-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2358-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2358-135">See also</span></span>

- [<span data-ttu-id="f2358-136">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2358-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="f2358-137">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2358-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
