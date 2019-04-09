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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2903395f5f834f2435b14d0b3f3e8bfe24af2867
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183054"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="5df98-102">IAppDomainBinding::OnAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="5df98-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="5df98-103">共通言語ランタイム (CLR) に、ホスト アプリケーション ドメインが作成されたことを通知するによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5df98-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df98-104">構文</span><span class="sxs-lookup"><span data-stu-id="5df98-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5df98-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5df98-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="5df98-106">[in]ポインター、 [IUnknown](/cpp/atl/iunknown)新しいアプリケーション ドメインを表すインターフェイス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5df98-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5df98-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="5df98-107">Requirements</span></span>  
 <span data-ttu-id="5df98-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5df98-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5df98-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5df98-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5df98-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5df98-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5df98-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5df98-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5df98-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5df98-112">See also</span></span>

- [<span data-ttu-id="5df98-113">IAppDomainBinding インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5df98-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
