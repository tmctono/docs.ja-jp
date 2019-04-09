---
title: ICLRHostProtectionManager::SetEagerSerializeGrantSets メソッド
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160e31859e3d58812861d4462e77d68fa18d6186
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079657"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="9386a-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets メソッド</span><span class="sxs-lookup"><span data-stu-id="9386a-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="9386a-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="9386a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9386a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9386a-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9386a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="9386a-105">Return Value</span></span>  
  
|<span data-ttu-id="9386a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9386a-106">HRESULT</span></span>|<span data-ttu-id="9386a-107">説明</span><span class="sxs-lookup"><span data-stu-id="9386a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9386a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9386a-108">S_OK</span></span>|`SetEagerSerializeGrantSets` <span data-ttu-id="9386a-109">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9386a-109">returned successfully.</span></span>|  
|<span data-ttu-id="9386a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9386a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9386a-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9386a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9386a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9386a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9386a-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9386a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9386a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9386a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9386a-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9386a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9386a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9386a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9386a-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9386a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9386a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9386a-118">E_FAIL</span></span>|<span data-ttu-id="9386a-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9386a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9386a-120">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9386a-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9386a-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9386a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9386a-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="9386a-122">Requirements</span></span>  
 <span data-ttu-id="9386a-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9386a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9386a-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9386a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9386a-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9386a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9386a-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9386a-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9386a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9386a-127">See also</span></span>

- [<span data-ttu-id="9386a-128">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9386a-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9386a-129">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9386a-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
