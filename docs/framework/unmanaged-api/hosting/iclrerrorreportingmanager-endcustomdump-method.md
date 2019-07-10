---
title: ICLRErrorReportingManager::EndCustomDump メソッド
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c2d2e5454a26111748f9676cfe1ce5caa76cad5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772839"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="ae68b-102">ICLRErrorReportingManager::EndCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="ae68b-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="ae68b-103">以前の呼び出しで指定されたカスタム スタック ダンプの構成を削除、 [iclrerrorreportingmanager::begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ae68b-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae68b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae68b-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ae68b-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="ae68b-105">Return Value</span></span>  
  
|<span data-ttu-id="ae68b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae68b-106">HRESULT</span></span>|<span data-ttu-id="ae68b-107">説明</span><span class="sxs-lookup"><span data-stu-id="ae68b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae68b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae68b-108">S_OK</span></span>|<span data-ttu-id="ae68b-109">`EndCustomDump` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ae68b-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="ae68b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae68b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae68b-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="ae68b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ae68b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ae68b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ae68b-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="ae68b-113">The call timed out.</span></span>|  
|<span data-ttu-id="ae68b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ae68b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ae68b-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ae68b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ae68b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ae68b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ae68b-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ae68b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ae68b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae68b-118">E_FAIL</span></span>|<span data-ttu-id="ae68b-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae68b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ae68b-120">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ae68b-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ae68b-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ae68b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae68b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae68b-122">Remarks</span></span>  
 <span data-ttu-id="ae68b-123">`EndCustomDump`メソッドはカスタム スタック ダンプ構成を以前の呼び出しで設定を消去、`BeginCustomDump`メソッドと、関連付けられた状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="ae68b-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="ae68b-124">これはカスタム スタック ダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae68b-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae68b-125">呼び出しに失敗する`EndCustomDump`によりメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="ae68b-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae68b-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae68b-126">Requirements</span></span>  
 <span data-ttu-id="ae68b-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae68b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae68b-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ae68b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae68b-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ae68b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae68b-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae68b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae68b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae68b-131">See also</span></span>

- [<span data-ttu-id="ae68b-132">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="ae68b-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="ae68b-133">ECustomDumpFlavor 列挙型</span><span class="sxs-lookup"><span data-stu-id="ae68b-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="ae68b-134">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae68b-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
