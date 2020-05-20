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
ms.openlocfilehash: e911a8e73020321511da5bd7f3ade677058048e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703825"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="f91e9-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets メソッド</span><span class="sxs-lookup"><span data-stu-id="f91e9-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="f91e9-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="f91e9-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f91e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="f91e9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f91e9-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f91e9-105">Return Value</span></span>  
  
|<span data-ttu-id="f91e9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f91e9-106">HRESULT</span></span>|<span data-ttu-id="f91e9-107">説明</span><span class="sxs-lookup"><span data-stu-id="f91e9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f91e9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f91e9-108">S_OK</span></span>|<span data-ttu-id="f91e9-109">`SetEagerSerializeGrantSets`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f91e9-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="f91e9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f91e9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f91e9-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f91e9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f91e9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f91e9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f91e9-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f91e9-113">The call timed out.</span></span>|  
|<span data-ttu-id="f91e9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f91e9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f91e9-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f91e9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f91e9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f91e9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f91e9-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f91e9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f91e9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f91e9-118">E_FAIL</span></span>|<span data-ttu-id="f91e9-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f91e9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f91e9-120">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f91e9-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f91e9-121">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f91e9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f91e9-122">要件</span><span class="sxs-lookup"><span data-stu-id="f91e9-122">Requirements</span></span>  
 <span data-ttu-id="f91e9-123">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f91e9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f91e9-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f91e9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f91e9-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f91e9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f91e9-126">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f91e9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91e9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f91e9-127">See also</span></span>

- [<span data-ttu-id="f91e9-128">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f91e9-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f91e9-129">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f91e9-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
