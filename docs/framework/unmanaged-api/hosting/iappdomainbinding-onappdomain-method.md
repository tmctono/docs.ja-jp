---
title: IAppDomainBinding::OnAppDomain メソッド
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
ms.openlocfilehash: 37c02b878cd52034603ab6cafe4d8aaca594cbe9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126880"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="0a687-102">IAppDomainBinding::OnAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="0a687-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="0a687-103">アプリケーションドメインが作成されたことをホストに通知するために、共通言語ランタイム (CLR) によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0a687-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a687-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a687-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a687-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a687-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="0a687-106">から新しいアプリケーションドメインを表す[IUnknown](/cpp/atl/iunknown)インターフェイスオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a687-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a687-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="0a687-107">Requirements</span></span>  
 <span data-ttu-id="0a687-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a687-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a687-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0a687-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a687-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0a687-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a687-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a687-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a687-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a687-112">See also</span></span>

- [<span data-ttu-id="0a687-113">IAppDomainBinding インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a687-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
