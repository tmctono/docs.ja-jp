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
ms.openlocfilehash: d69b12404459de5dbc1c7748deee6ca09c1e5182
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772415"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="e5d8a-102">EInitializeNewDomainFlags 列挙体</span><span class="sxs-lookup"><span data-stu-id="e5d8a-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="e5d8a-103">アプリケーション ドメインの初期化に関する情報をランタイムに提供するホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5d8a-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d8a-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5d8a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e5d8a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e5d8a-105">Members</span></span>  
  
|<span data-ttu-id="e5d8a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e5d8a-106">Member</span></span>|<span data-ttu-id="e5d8a-107">説明</span><span class="sxs-lookup"><span data-stu-id="e5d8a-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="e5d8a-108">フラグがありません。</span><span class="sxs-lookup"><span data-stu-id="e5d8a-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="e5d8a-109">共通言語ランタイム (CLR) を通知するホストを変更しないようにアプリケーション ドメインでのセキュリティの状態、<xref:System.AppDomainManager.InitializeNewDomain%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="e5d8a-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d8a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5d8a-110">Remarks</span></span>  
 <span data-ttu-id="e5d8a-111">[Iclrdomainmanager::setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)メソッドは、型のパラメーターを受け取る`EInitializeNewDomainFlags`します。</span><span class="sxs-lookup"><span data-stu-id="e5d8a-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d8a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5d8a-112">Requirements</span></span>  
 <span data-ttu-id="e5d8a-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5d8a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d8a-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5d8a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5d8a-115">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5d8a-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5d8a-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d8a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d8a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5d8a-117">See also</span></span>

- [<span data-ttu-id="e5d8a-118">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="e5d8a-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="e5d8a-119">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="e5d8a-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
