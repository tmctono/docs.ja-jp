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
ms.openlocfilehash: 798ef6a9b058d9d49019554feba63627360e6a0e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480040"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="a0bd4-102">IAppDomainBinding::OnAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="a0bd4-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="a0bd4-103">共通言語ランタイム (CLR) に、ホスト アプリケーション ドメインが作成されたことを通知するによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a0bd4-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0bd4-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0bd4-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0bd4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0bd4-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="a0bd4-106">[in]ポインター、 [IUnknown](/cpp/atl/iunknown)新しいアプリケーション ドメインを表すインターフェイス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a0bd4-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0bd4-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a0bd4-107">Requirements</span></span>  
 <span data-ttu-id="a0bd4-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0bd4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0bd4-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0bd4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0bd4-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a0bd4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0bd4-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0bd4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bd4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0bd4-112">See also</span></span>
- [<span data-ttu-id="a0bd4-113">IAppDomainBinding インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0bd4-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
