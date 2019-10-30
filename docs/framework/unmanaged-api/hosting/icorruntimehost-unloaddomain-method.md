---
title: ICorRuntimeHost::UnloadDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: dfdcb9b8aedeb3ccbbd27864e79ce43338942922
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133355"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="74790-102">ICorRuntimeHost::UnloadDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="74790-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="74790-103">現在のプロセスから、指定されたアプリケーションドメインをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="74790-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74790-104">構文</span><span class="sxs-lookup"><span data-stu-id="74790-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74790-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74790-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="74790-106">からアンロードするドメインを表す <xref:System._AppDomain?displayProperty=nameWithType> 型のポインター。</span><span class="sxs-lookup"><span data-stu-id="74790-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74790-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="74790-107">Return Value</span></span>  
  
|<span data-ttu-id="74790-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74790-108">HRESULT</span></span>|<span data-ttu-id="74790-109">説明</span><span class="sxs-lookup"><span data-stu-id="74790-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74790-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="74790-110">S_OK</span></span>|<span data-ttu-id="74790-111">操作は成功しました。</span><span class="sxs-lookup"><span data-stu-id="74790-111">The operation was successful.</span></span>|  
|<span data-ttu-id="74790-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="74790-112">S_FALSE</span></span>|<span data-ttu-id="74790-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="74790-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="74790-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74790-114">E_FAIL</span></span>|<span data-ttu-id="74790-115">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="74790-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="74790-116">メソッドから E_FAIL が返された場合、そのプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="74790-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="74790-117">後続のホスト Api への呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="74790-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74790-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74790-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74790-119">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="74790-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74790-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="74790-120">Requirements</span></span>  
 <span data-ttu-id="74790-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74790-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74790-122">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="74790-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74790-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="74790-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74790-124">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="74790-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74790-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="74790-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="74790-126">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74790-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
