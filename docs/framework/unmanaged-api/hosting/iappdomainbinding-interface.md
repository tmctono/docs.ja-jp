---
title: IAppDomainBinding インターフェイス
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
ms.openlocfilehash: cf4fa9c5ec35391a0e772e25112f305bfa6e1564
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126901"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="1f163-102">IAppDomainBinding インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f163-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="1f163-103">アプリケーションドメインが作成されたことをホストアプリケーションに通知するために、共通言語ランタイム (CLR) によって呼び出されるメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f163-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f163-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1f163-104">Methods</span></span>  
  
|<span data-ttu-id="1f163-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1f163-105">Method</span></span>|<span data-ttu-id="1f163-106">説明</span><span class="sxs-lookup"><span data-stu-id="1f163-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f163-107">OnAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="1f163-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="1f163-108">アプリケーションドメインが作成されたことをホストに通知するために、共通言語ランタイム (CLR) によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1f163-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f163-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="1f163-109">Requirements</span></span>  
 <span data-ttu-id="1f163-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f163-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f163-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1f163-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f163-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1f163-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f163-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f163-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f163-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f163-114">See also</span></span>

- [<span data-ttu-id="1f163-115">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f163-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
