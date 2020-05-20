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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616230"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="3de3d-102">EInitializeNewDomainFlags 列挙体</span><span class="sxs-lookup"><span data-stu-id="3de3d-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="3de3d-103">ホストがアプリケーションドメインの初期化に関する情報をランタイムに提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3de3d-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3de3d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3de3d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3de3d-105">Members</span></span>  
  
|<span data-ttu-id="3de3d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3de3d-106">Member</span></span>|<span data-ttu-id="3de3d-107">説明</span><span class="sxs-lookup"><span data-stu-id="3de3d-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="3de3d-108">フラグなし。</span><span class="sxs-lookup"><span data-stu-id="3de3d-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="3de3d-109">ホストがメソッド内のアプリケーションドメインのセキュリティ状態に変更を加えないことを、共通言語ランタイム (CLR) に通知し <xref:System.AppDomainManager.InitializeNewDomain%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3de3d-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3de3d-110">解説</span><span class="sxs-lookup"><span data-stu-id="3de3d-110">Remarks</span></span>  
 <span data-ttu-id="3de3d-111">[ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)メソッドは、型のパラメーターを受け取り `EInitializeNewDomainFlags` ます。</span><span class="sxs-lookup"><span data-stu-id="3de3d-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de3d-112">要件</span><span class="sxs-lookup"><span data-stu-id="3de3d-112">Requirements</span></span>  
 <span data-ttu-id="3de3d-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3de3d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de3d-114">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3de3d-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3de3d-115">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3de3d-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3de3d-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de3d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de3d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3de3d-117">See also</span></span>

- [<span data-ttu-id="3de3d-118">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="3de3d-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="3de3d-119">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="3de3d-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
