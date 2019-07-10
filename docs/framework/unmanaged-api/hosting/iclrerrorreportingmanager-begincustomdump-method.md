---
title: ICLRErrorReportingManager::BeginCustomDump メソッド
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d0a85607586a8cdf0a319f2e43d9815d24be21b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772918"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="23e1b-102">ICLRErrorReportingManager::BeginCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="23e1b-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="23e1b-103">エラー報告用にカスタムのヒープ ダンプの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="23e1b-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23e1b-104">構文</span><span class="sxs-lookup"><span data-stu-id="23e1b-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23e1b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23e1b-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="23e1b-106">[in]A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)カスタム ヒープ ダンプを構築するときのヒープ ダンプの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="23e1b-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="23e1b-107">[in]長さ、`items`配列。</span><span class="sxs-lookup"><span data-stu-id="23e1b-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="23e1b-108">場合`dwFlavor`DUMP_FLAVOR_Mini でない`dwNumItems`0 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23e1b-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="23e1b-109">[in]配列の[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)インスタンス、ミニ ダンプに追加する項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="23e1b-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="23e1b-110">場合`dwFlavor`が DUMP_FLAVOR_Mini、 `items` null にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23e1b-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="23e1b-111">[in]将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="23e1b-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23e1b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="23e1b-112">Return Value</span></span>  
  
|<span data-ttu-id="23e1b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23e1b-113">HRESULT</span></span>|<span data-ttu-id="23e1b-114">説明</span><span class="sxs-lookup"><span data-stu-id="23e1b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23e1b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="23e1b-115">S_OK</span></span>|<span data-ttu-id="23e1b-116">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="23e1b-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="23e1b-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23e1b-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23e1b-118">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="23e1b-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23e1b-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23e1b-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23e1b-120">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="23e1b-120">The call timed out.</span></span>|  
|<span data-ttu-id="23e1b-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23e1b-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23e1b-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="23e1b-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23e1b-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23e1b-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23e1b-124">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="23e1b-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23e1b-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23e1b-125">E_FAIL</span></span>|<span data-ttu-id="23e1b-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="23e1b-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23e1b-127">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="23e1b-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23e1b-128">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="23e1b-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23e1b-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="23e1b-129">Remarks</span></span>  
 <span data-ttu-id="23e1b-130">`BeginCustomDump`メソッドは、カスタム ヒープ ダンプ構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="23e1b-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="23e1b-131">[EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)メソッドは、カスタム ヒープ ダンプ構成をクリアし、関連付けられている状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="23e1b-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="23e1b-132">これは、カスタム ヒープ ダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="23e1b-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23e1b-133">呼び出しに失敗する`EndCustomDump`によりメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="23e1b-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23e1b-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="23e1b-134">Requirements</span></span>  
 <span data-ttu-id="23e1b-135">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23e1b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23e1b-136">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23e1b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23e1b-137">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="23e1b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23e1b-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23e1b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e1b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="23e1b-139">See also</span></span>

- [<span data-ttu-id="23e1b-140">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="23e1b-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="23e1b-141">ECustomDumpFlavor 列挙型</span><span class="sxs-lookup"><span data-stu-id="23e1b-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="23e1b-142">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23e1b-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
