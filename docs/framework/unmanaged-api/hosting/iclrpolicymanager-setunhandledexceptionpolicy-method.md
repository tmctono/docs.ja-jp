---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7fa02c4c79da118543117aada7d1b9cca09c4cae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703407"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="73a50-102">ICLRPolicyManager::SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="73a50-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="73a50-103">未処理の例外が発生した場合の共通言語ランタイム (CLR) の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="73a50-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a50-104">構文</span><span class="sxs-lookup"><span data-stu-id="73a50-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73a50-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73a50-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="73a50-106">から[EClrUnhandledException](eclrunhandledexception-enumeration.md)値の1つ。動作が CLR またはホストによって設定されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="73a50-106">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73a50-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="73a50-107">Return Value</span></span>  
  
|<span data-ttu-id="73a50-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73a50-108">HRESULT</span></span>|<span data-ttu-id="73a50-109">説明</span><span class="sxs-lookup"><span data-stu-id="73a50-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73a50-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="73a50-110">S_OK</span></span>|<span data-ttu-id="73a50-111">`SetUnhandledExceptionPolicy`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="73a50-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="73a50-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73a50-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73a50-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="73a50-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73a50-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73a50-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73a50-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="73a50-115">The call timed out.</span></span>|  
|<span data-ttu-id="73a50-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73a50-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73a50-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="73a50-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73a50-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73a50-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73a50-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="73a50-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73a50-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73a50-120">E_FAIL</span></span>|<span data-ttu-id="73a50-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="73a50-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73a50-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="73a50-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73a50-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="73a50-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a50-124">解説</span><span class="sxs-lookup"><span data-stu-id="73a50-124">Remarks</span></span>  
 <span data-ttu-id="73a50-125">既定では、CLR はすべてのハンドルされない例外の最終的なハンドラーであり、既定の動作では、プロセスが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="73a50-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="73a50-126">ホストはこの動作を変更できます。そのためには、 `policy` 値を Ehost決定 Edpolicy に設定します。</span><span class="sxs-lookup"><span data-stu-id="73a50-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="73a50-127">この値により、ホストは、以前のバージョンの CLR の場合と同様に、独自の既定の動作を実装できます。</span><span class="sxs-lookup"><span data-stu-id="73a50-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73a50-128">要件</span><span class="sxs-lookup"><span data-stu-id="73a50-128">Requirements</span></span>  
 <span data-ttu-id="73a50-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73a50-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73a50-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="73a50-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73a50-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="73a50-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73a50-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73a50-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a50-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="73a50-133">See also</span></span>

- [<span data-ttu-id="73a50-134">EClrUnhandledException 列挙型</span><span class="sxs-lookup"><span data-stu-id="73a50-134">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="73a50-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a50-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="73a50-136">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a50-136">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="73a50-137">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73a50-137">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
