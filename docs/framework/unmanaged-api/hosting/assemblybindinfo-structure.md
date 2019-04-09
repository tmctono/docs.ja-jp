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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce79987c7fcf45b8d10dcc4613e053ee735941de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112815"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="9f28e-102">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="9f28e-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="9f28e-103">参照アセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9f28e-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f28e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f28e-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="9f28e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9f28e-105">Members</span></span>  
  
|<span data-ttu-id="9f28e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9f28e-106">Member</span></span>|<span data-ttu-id="9f28e-107">説明</span><span class="sxs-lookup"><span data-stu-id="9f28e-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="9f28e-108">一意の識別子、`IStream`への呼び出しによって返される[ihostassemblystore::provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)、参照アセンブリが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="9f28e-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="9f28e-109">参照アセンブリの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="9f28e-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="9f28e-110">バインディング ポリシー値を適用した後、参照先アセンブリの識別子。</span><span class="sxs-lookup"><span data-stu-id="9f28e-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="9f28e-111">1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)されるバージョン管理ポリシー、適用するかどう参照されるアセンブリを示す値。</span><span class="sxs-lookup"><span data-stu-id="9f28e-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f28e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f28e-112">Remarks</span></span>  
 <span data-ttu-id="9f28e-113">ホスト提供の一意識別子`dwAppDomainId`共通言語ランタイム (CLR) にします。</span><span class="sxs-lookup"><span data-stu-id="9f28e-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="9f28e-114">呼び出しの後に`IHostAssemblyStore::ProvideAssembly`、ランタイムでは、識別子を使用して判断を返すかどうかの内容、`IStream`マップされています。</span><span class="sxs-lookup"><span data-stu-id="9f28e-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="9f28e-115">そうである場合、ランタイムは、ストリームを再マップするのではなく、既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9f28e-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="9f28e-116">ランタイムも識別子を使用してこのルックアップ キーとしてから返されるストリームの呼び出しを[ihostassemblystore::providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f28e-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="9f28e-117">そのため、識別子は、モジュールの要求とアセンブリの要求で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f28e-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f28e-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="9f28e-118">Requirements</span></span>  
 <span data-ttu-id="9f28e-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f28e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f28e-120">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="9f28e-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9f28e-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9f28e-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9f28e-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9f28e-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f28e-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f28e-123">See also</span></span>

- [<span data-ttu-id="9f28e-124">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="9f28e-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="9f28e-125">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f28e-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9f28e-126">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f28e-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9f28e-127">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f28e-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="9f28e-128">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f28e-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="9f28e-129">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="9f28e-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
