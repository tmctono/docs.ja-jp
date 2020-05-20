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
ms.openlocfilehash: 2d5dbd003d0ea5decae0025d47e6bd5c1fb1ed4a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617075"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="86e9a-102">IAppDomainBinding::OnAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="86e9a-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="86e9a-103">アプリケーションドメインが作成されたことをホストに通知するために、共通言語ランタイム (CLR) によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="86e9a-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="86e9a-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86e9a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86e9a-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="86e9a-106">から新しいアプリケーションドメインを表す[IUnknown](/cpp/atl/iunknown)インターフェイスオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="86e9a-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e9a-107">要件</span><span class="sxs-lookup"><span data-stu-id="86e9a-107">Requirements</span></span>  
 <span data-ttu-id="86e9a-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86e9a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e9a-109">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="86e9a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86e9a-110">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="86e9a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86e9a-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e9a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e9a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="86e9a-112">See also</span></span>

- [<span data-ttu-id="86e9a-113">IAppDomainBinding インターフェイス</span><span class="sxs-lookup"><span data-stu-id="86e9a-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
