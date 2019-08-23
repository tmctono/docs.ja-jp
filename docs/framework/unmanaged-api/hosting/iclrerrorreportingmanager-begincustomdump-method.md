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
ms.openlocfilehash: 98eebd489792f57f7f98d3596d4f25be2e847441
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966276"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="4224b-102">ICLRErrorReportingManager::BeginCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="4224b-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="4224b-103">エラー報告のためのカスタムヒープダンプの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="4224b-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4224b-104">構文</span><span class="sxs-lookup"><span data-stu-id="4224b-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4224b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4224b-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="4224b-106">からカスタムヒープダンプを構築するときに使用するヒープダンプの種類を示す[ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)値です。</span><span class="sxs-lookup"><span data-stu-id="4224b-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="4224b-107">から`items`配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="4224b-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="4224b-108">が`dwFlavor` DUMP_FLAVOR_Mini でない場合`dwNumItems`は、を0にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4224b-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="4224b-109">からミニダンプに追加する項目を指定する、 [Customdumpitem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)インスタンスの配列。</span><span class="sxs-lookup"><span data-stu-id="4224b-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="4224b-110">が`dwFlavor` DUMP_FLAVOR_Mini でない場合`items`は、を null にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4224b-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="4224b-111">から将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="4224b-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4224b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="4224b-112">Return Value</span></span>  
  
|<span data-ttu-id="4224b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4224b-113">HRESULT</span></span>|<span data-ttu-id="4224b-114">説明</span><span class="sxs-lookup"><span data-stu-id="4224b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4224b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4224b-115">S_OK</span></span>|<span data-ttu-id="4224b-116">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4224b-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="4224b-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4224b-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4224b-118">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4224b-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4224b-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4224b-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4224b-120">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4224b-120">The call timed out.</span></span>|  
|<span data-ttu-id="4224b-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4224b-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4224b-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4224b-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4224b-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4224b-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4224b-124">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4224b-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4224b-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4224b-125">E_FAIL</span></span>|<span data-ttu-id="4224b-126">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4224b-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4224b-127">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4224b-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4224b-128">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4224b-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4224b-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="4224b-129">Remarks</span></span>  
 <span data-ttu-id="4224b-130">メソッド`BeginCustomDump`は、カスタムヒープダンプ構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="4224b-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="4224b-131">[Endcustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)メソッドは、カスタムヒープダンプ構成をクリアし、関連付けられているすべての状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="4224b-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="4224b-132">カスタムヒープダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4224b-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4224b-133">を呼び出さ`EndCustomDump`ないと、メモリがリークします。</span><span class="sxs-lookup"><span data-stu-id="4224b-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4224b-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="4224b-134">Requirements</span></span>  
 <span data-ttu-id="4224b-135">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4224b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4224b-136">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4224b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4224b-137">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4224b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4224b-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4224b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4224b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="4224b-139">See also</span></span>

- [<span data-ttu-id="4224b-140">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="4224b-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="4224b-141">ECustomDumpFlavor 列挙型</span><span class="sxs-lookup"><span data-stu-id="4224b-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="4224b-142">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4224b-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
