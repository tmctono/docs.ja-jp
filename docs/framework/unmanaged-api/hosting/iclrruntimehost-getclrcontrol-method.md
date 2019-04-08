---
title: ICLRRuntimeHost::GetCLRControl メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83b029c24321946f777966daa7a486f9e8e7b7a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073149"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="15ae0-102">ICLRRuntimeHost::GetCLRControl メソッド</span><span class="sxs-lookup"><span data-stu-id="15ae0-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="15ae0-103">型のインターフェイス ポインターを取得[ICLRControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)ホストは、共通言語ランタイム (CLR) の部分をカスタマイズして使用できます。</span><span class="sxs-lookup"><span data-stu-id="15ae0-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ae0-104">構文</span><span class="sxs-lookup"><span data-stu-id="15ae0-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ae0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ae0-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="15ae0-106">[out]型のインターフェイス ポインターを[ICLRControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)CLR の他の側面を構成するホストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="15ae0-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15ae0-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="15ae0-107">Return Value</span></span>  
  
|<span data-ttu-id="15ae0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15ae0-108">HRESULT</span></span>|<span data-ttu-id="15ae0-109">説明</span><span class="sxs-lookup"><span data-stu-id="15ae0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15ae0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="15ae0-110">S_OK</span></span>|`GetCLRControl` <span data-ttu-id="15ae0-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="15ae0-111">returned successfully.</span></span>|  
|<span data-ttu-id="15ae0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15ae0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15ae0-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="15ae0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15ae0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15ae0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15ae0-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="15ae0-115">The call timed out.</span></span>|  
|<span data-ttu-id="15ae0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15ae0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15ae0-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="15ae0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15ae0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15ae0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15ae0-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="15ae0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15ae0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15ae0-120">E_FAIL</span></span>|<span data-ttu-id="15ae0-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="15ae0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15ae0-122">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="15ae0-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15ae0-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="15ae0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15ae0-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="15ae0-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="15ae0-125">CLR は既に開始しています。</span><span class="sxs-lookup"><span data-stu-id="15ae0-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15ae0-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="15ae0-126">Remarks</span></span>  
 `ICLRControl` <span data-ttu-id="15ae0-127">提供、 [GetCLRManager メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)メソッドで、ホストが、マネージャーの種類のいずれかにインターフェイス ポインターを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="15ae0-127">provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ae0-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="15ae0-128">Requirements</span></span>  
 <span data-ttu-id="15ae0-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ae0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ae0-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15ae0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15ae0-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="15ae0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="15ae0-132">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="15ae0-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15ae0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="15ae0-133">See also</span></span>

- [<span data-ttu-id="15ae0-134">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15ae0-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="15ae0-135">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15ae0-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
