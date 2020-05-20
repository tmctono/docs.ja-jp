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
ms.openlocfilehash: 704d8d0921e671e4172fa6e0ae3f14c4908f289a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615658"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="4500e-102">ICLRErrorReportingManager::EndCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="4500e-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="4500e-103">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)メソッドの以前の呼び出しで指定されたカスタムスタックダンプ構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="4500e-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4500e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4500e-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4500e-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="4500e-105">Return Value</span></span>  
  
|<span data-ttu-id="4500e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4500e-106">HRESULT</span></span>|<span data-ttu-id="4500e-107">説明</span><span class="sxs-lookup"><span data-stu-id="4500e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4500e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4500e-108">S_OK</span></span>|<span data-ttu-id="4500e-109">`EndCustomDump`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4500e-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="4500e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4500e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4500e-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4500e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4500e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4500e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4500e-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4500e-113">The call timed out.</span></span>|  
|<span data-ttu-id="4500e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4500e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4500e-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4500e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4500e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4500e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4500e-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4500e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4500e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4500e-118">E_FAIL</span></span>|<span data-ttu-id="4500e-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4500e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4500e-120">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4500e-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4500e-121">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4500e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4500e-122">解説</span><span class="sxs-lookup"><span data-stu-id="4500e-122">Remarks</span></span>  
 <span data-ttu-id="4500e-123">メソッドは、 `EndCustomDump` メソッドの以前の呼び出しによって設定されたカスタムスタックダンプ構成をクリア `BeginCustomDump` し、関連付けられているすべての状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="4500e-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="4500e-124">カスタムスタックダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4500e-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4500e-125">を呼び出さない `EndCustomDump` と、メモリがリークします。</span><span class="sxs-lookup"><span data-stu-id="4500e-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4500e-126">要件</span><span class="sxs-lookup"><span data-stu-id="4500e-126">Requirements</span></span>  
 <span data-ttu-id="4500e-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4500e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4500e-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4500e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4500e-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4500e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4500e-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4500e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4500e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4500e-131">See also</span></span>

- [<span data-ttu-id="4500e-132">CustomDumpItem 構造体</span><span class="sxs-lookup"><span data-stu-id="4500e-132">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="4500e-133">ECustomDumpFlavor 列挙型</span><span class="sxs-lookup"><span data-stu-id="4500e-133">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="4500e-134">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4500e-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
