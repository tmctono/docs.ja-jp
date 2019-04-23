---
title: EInitializeNewDomainFlags 列挙体
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b0d9989d66888c33de0359e4c93529fcfbf8d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095361"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="c12aa-102">EInitializeNewDomainFlags 列挙体</span><span class="sxs-lookup"><span data-stu-id="c12aa-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="c12aa-103">アプリケーション ドメインの初期化に関する情報をランタイムに提供するホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c12aa-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="c12aa-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c12aa-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c12aa-105">Members</span></span>  
  
|<span data-ttu-id="c12aa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c12aa-106">Member</span></span>|<span data-ttu-id="c12aa-107">説明</span><span class="sxs-lookup"><span data-stu-id="c12aa-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="c12aa-108">フラグがありません。</span><span class="sxs-lookup"><span data-stu-id="c12aa-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="c12aa-109">共通言語ランタイム (CLR) を通知するホストを変更しないようにアプリケーション ドメインでのセキュリティの状態、<xref:System.AppDomainManager.InitializeNewDomain%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c12aa-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c12aa-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c12aa-110">Remarks</span></span>  
 <span data-ttu-id="c12aa-111">[Iclrdomainmanager::setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)メソッドは、型のパラメーターを受け取る`EInitializeNewDomainFlags`します。</span><span class="sxs-lookup"><span data-stu-id="c12aa-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12aa-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c12aa-112">Requirements</span></span>  
 <span data-ttu-id="c12aa-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12aa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c12aa-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c12aa-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c12aa-115">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c12aa-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c12aa-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12aa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12aa-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c12aa-117">See also</span></span>

- [<span data-ttu-id="c12aa-118">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="c12aa-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="c12aa-119">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="c12aa-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
