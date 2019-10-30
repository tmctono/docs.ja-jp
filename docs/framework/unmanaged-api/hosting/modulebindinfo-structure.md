---
title: ModuleBindInfo 構造体
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133745"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="a9f05-102">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="a9f05-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="a9f05-103">参照されるモジュールとそれを含むアセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9f05-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f05-104">構文</span><span class="sxs-lookup"><span data-stu-id="a9f05-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="a9f05-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a9f05-105">Members</span></span>  
  
|<span data-ttu-id="a9f05-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a9f05-106">Member</span></span>|<span data-ttu-id="a9f05-107">説明</span><span class="sxs-lookup"><span data-stu-id="a9f05-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="a9f05-108">参照先のモジュールを読み込む[IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)メソッドの呼び出しによって返される `IStream` の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a9f05-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="a9f05-109">参照されたモジュールを含むアセンブリの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a9f05-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="a9f05-110">参照されているモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="a9f05-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9f05-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9f05-111">Remarks</span></span>  
 <span data-ttu-id="a9f05-112">`ModuleBindInfo` は、`IHostAssemblyStore::ProvideModule`にパラメーターとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="a9f05-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="a9f05-113">ホストは、共通言語ランタイム (CLR) に `dwAppDomainId` 一意の識別子を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9f05-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="a9f05-114">[IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)メソッドの呼び出しが返されると、ランタイムは識別子を使用して、`IStream` の内容がマップされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a9f05-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="a9f05-115">その場合、ランタイムはストリームを再マップするのではなく、既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a9f05-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="a9f05-116">また、ランタイムは、`IHostAssemblyStore::ProvideAssembly` メソッドへの呼び出しから返されるストリームの参照キーとして、この識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9f05-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="a9f05-117">このため、識別子は、モジュール要求とアセンブリ要求に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9f05-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f05-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="a9f05-118">Requirements</span></span>  
 <span data-ttu-id="a9f05-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f05-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f05-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a9f05-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a9f05-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a9f05-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9f05-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f05-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f05-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9f05-123">See also</span></span>

- [<span data-ttu-id="a9f05-124">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="a9f05-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="a9f05-125">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="a9f05-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="a9f05-126">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9f05-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a9f05-127">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9f05-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a9f05-128">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9f05-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
