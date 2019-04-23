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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086456"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="a7f9b-102">EApiCategories 列挙型</span><span class="sxs-lookup"><span data-stu-id="a7f9b-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="a7f9b-103">ホストが部分的に信頼されたコードでの実行をブロックできる機能のカテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7f9b-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="a7f9b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a7f9b-105">Members</span></span>  
  
|<span data-ttu-id="a7f9b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a7f9b-106">Member</span></span>|<span data-ttu-id="a7f9b-107">説明</span><span class="sxs-lookup"><span data-stu-id="a7f9b-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="a7f9b-108">クラスとその他で対応されるメンバーをすべて管理を指定します。`EApiCategories`フィールドは、部分的に信頼されたコードでの実行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="a7f9b-109">マネージ クラスとメンバーを作成、操作、および外部プロセスの破棄を部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="a7f9b-110">マネージ クラスとメンバーを作成、操作、および外部のスレッドの破棄を部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="a7f9b-111">マネージ型と中止にメモリをリークでした可能性のあるメンバーを部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="a7f9b-112">部分的に信頼されたコードでの実行をブロックするマネージ コードのカテゴリがないを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="a7f9b-113">共通言語ランタイム (CLR) のセキュリティ インフラストラクチャを部分的に信頼されたコードによって使用されるをブロックするように指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="a7f9b-114">マネージ クラスとメンバーの機能を持つホストされたプロセスに影響する可能性を部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="a7f9b-115">マネージ クラスとメンバーの機能を持つホストされるプロセスのスレッドに影響する可能性を部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="a7f9b-116">マネージ クラスおよび共有状態を公開するメンバーを部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="a7f9b-117">共通言語ランタイム クラスとユーザー コードがロックを保持するメンバーを部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="a7f9b-118">マネージ クラスとメンバーを許可または人による操作を必要とするが部分的に信頼されたコードの実行をブロックすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7f9b-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7f9b-119">Remarks</span></span>  
 <span data-ttu-id="a7f9b-120">[Iclrhostprotectionmanager::setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)メソッドは、型のパラメーターを受け取る`EApiCategories`します。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="a7f9b-121">`EApiCategories`列挙と`SetProtectedCategories`メソッドは直接関係をマネージ<xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType>クラス。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a7f9b-122">マネージ クラスを併用、<xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>列挙型、値が対応に直接、`EApiCategories`を記載したカテゴリに対応する機能を公開するマネージ型とメンバーをマークする、値`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7f9b-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="a7f9b-123">Requirements</span></span>  
 <span data-ttu-id="a7f9b-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f9b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7f9b-125">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7f9b-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7f9b-126">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7f9b-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7f9b-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7f9b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f9b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7f9b-128">See also</span></span>

- [<span data-ttu-id="a7f9b-129">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a7f9b-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="a7f9b-130">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="a7f9b-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
