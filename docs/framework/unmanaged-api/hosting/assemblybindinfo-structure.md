---
title: AssemblyBindInfo 構造体
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192114"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="e2e45-102">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="e2e45-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="e2e45-103">参照アセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2e45-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e45-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2e45-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="e2e45-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e2e45-105">Members</span></span>  
  
|<span data-ttu-id="e2e45-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e2e45-106">Member</span></span>|<span data-ttu-id="e2e45-107">説明</span><span class="sxs-lookup"><span data-stu-id="e2e45-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="e2e45-108">参照されるアセンブリの読み込み元である[IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)への呼び出しによって返される `IStream` の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e2e45-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="e2e45-109">参照アセンブリの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e2e45-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="e2e45-110">バインドポリシー値の適用後に参照されるアセンブリの識別子。</span><span class="sxs-lookup"><span data-stu-id="e2e45-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="e2e45-111">参照先のアセンブリに適用するバージョン管理ポリシーを示す[Epolicyaction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="e2e45-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2e45-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2e45-112">Remarks</span></span>  
 <span data-ttu-id="e2e45-113">ホストは、共通言語ランタイム (CLR) に `dwAppDomainId` 一意の識別子を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2e45-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="e2e45-114">`IHostAssemblyStore::ProvideAssembly` の呼び出しが返されると、ランタイムは識別子を使用して、`IStream` の内容がマップされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e2e45-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="e2e45-115">その場合、ランタイムはストリームを再マップするのではなく、既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e2e45-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="e2e45-116">ランタイムは、 [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)への呼び出しから返されたストリームの参照キーとしても、この識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2e45-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="e2e45-117">このため、識別子はモジュール要求とアセンブリ要求に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2e45-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e45-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="e2e45-118">Requirements</span></span>  
 <span data-ttu-id="e2e45-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2e45-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e45-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e2e45-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e2e45-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e2e45-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2e45-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e45-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e45-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2e45-123">See also</span></span>

- [<span data-ttu-id="e2e45-124">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="e2e45-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="e2e45-125">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2e45-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e2e45-126">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2e45-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e2e45-127">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2e45-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="e2e45-128">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2e45-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="e2e45-129">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="e2e45-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
