---
title: EApiCategories 列挙型
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131214"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="fdeae-102">EApiCategories 列挙型</span><span class="sxs-lookup"><span data-stu-id="fdeae-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="fdeae-103">部分的に信頼されたコードでホストが実行をブロックできる機能のカテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdeae-104">構文</span><span class="sxs-lookup"><span data-stu-id="fdeae-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="fdeae-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fdeae-105">Members</span></span>  
  
|<span data-ttu-id="fdeae-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fdeae-106">Member</span></span>|<span data-ttu-id="fdeae-107">説明</span><span class="sxs-lookup"><span data-stu-id="fdeae-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="fdeae-108">他の `EApiCategories` フィールドの対象となるすべてのマネージクラスおよびメンバーが、部分的に信頼されたコードで実行されないようにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="fdeae-109">外部プロセスの作成、操作、および破棄を許可するマネージクラスおよびメンバーが、部分的に信頼されたコードでの実行をブロックされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="fdeae-110">外部スレッドの作成、操作、および破棄を許可するマネージクラスおよびメンバーが、部分的に信頼されたコードでの実行をブロックされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="fdeae-111">中止時にメモリをリークする可能性のあるマネージ型およびメンバーが、部分的に信頼されたコードで実行されないようにブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="fdeae-112">部分的に信頼されたコードでは、マネージコードのカテゴリの実行をブロックしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="fdeae-113">共通言語ランタイム (CLR) のセキュリティインフラストラクチャが、部分的に信頼されたコードによって使用されるのをブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="fdeae-114">ホストされるプロセスに影響を与える可能性があるマネージクラスおよびメンバーが、部分的に信頼されたコードで実行されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="fdeae-115">ホストされているプロセスのスレッドに影響を与える可能性のあるマネージクラスおよびメンバーが、部分的に信頼されたコードでの実行をブロックされるように指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="fdeae-116">マネージクラスおよび共有状態を公開するメンバーが、部分的に信頼されたコードで実行されないようにブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="fdeae-117">ユーザーコードがロックを保持することを許可する共通言語ランタイムクラスおよびメンバーが、部分的に信頼されたコードでの実行をブロックするように指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="fdeae-118">人間の操作を許可または必要とするマネージクラスおよびメンバーが、部分的に信頼されたコードでの実行をブロックされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdeae-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdeae-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="fdeae-119">Remarks</span></span>  
 <span data-ttu-id="fdeae-120">[ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)メソッドは、型 `EApiCategories`のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fdeae-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="fdeae-121">`EApiCategories` 列挙体と `SetProtectedCategories` メソッドは、マネージ <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> クラスに直接関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="fdeae-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="fdeae-122">マネージクラスは、`EApiCategories`によって記述されたカテゴリに対応する機能を公開するマネージ型およびメンバーをマークするために、値が `EApiCategories` 値に直接対応する <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 列挙体と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fdeae-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdeae-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="fdeae-123">Requirements</span></span>  
 <span data-ttu-id="fdeae-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdeae-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdeae-125">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fdeae-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdeae-126">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fdeae-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdeae-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdeae-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdeae-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdeae-128">See also</span></span>

- [<span data-ttu-id="fdeae-129">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdeae-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="fdeae-130">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="fdeae-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
