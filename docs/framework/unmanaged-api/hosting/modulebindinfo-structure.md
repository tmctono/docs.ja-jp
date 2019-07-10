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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e0e877402daf27c375aedddf8922e919a546ae5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781174"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="db6c3-102">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="db6c3-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="db6c3-103">参照されるモジュールとそれを含んでいるアセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="db6c3-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6c3-104">構文</span><span class="sxs-lookup"><span data-stu-id="db6c3-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="db6c3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="db6c3-105">Members</span></span>  
  
|<span data-ttu-id="db6c3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="db6c3-106">Member</span></span>|<span data-ttu-id="db6c3-107">説明</span><span class="sxs-lookup"><span data-stu-id="db6c3-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="db6c3-108">一意の識別子、`IStream`への呼び出しによって返される、 [ihostassemblystore::providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)参照されるモジュールの読み込み元のメソッド。</span><span class="sxs-lookup"><span data-stu-id="db6c3-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="db6c3-109">参照されるモジュールを含むアセンブリの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="db6c3-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="db6c3-110">参照されるモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="db6c3-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db6c3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="db6c3-111">Remarks</span></span>  
 <span data-ttu-id="db6c3-112">`ModuleBindInfo` パラメーターとして渡される`IHostAssemblyStore::ProvideModule`します。</span><span class="sxs-lookup"><span data-stu-id="db6c3-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="db6c3-113">ホスト提供の一意識別子`dwAppDomainId`共通言語ランタイム (CLR) にします。</span><span class="sxs-lookup"><span data-stu-id="db6c3-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="db6c3-114">呼び出しの後に、 [ihostassemblystore::provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)ランタイム識別子を使用して判断するメソッドが返されるかどうかの内容、`IStream`マップされています。</span><span class="sxs-lookup"><span data-stu-id="db6c3-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="db6c3-115">そうである場合、ランタイムは、ストリームを再マップするのではなく、既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="db6c3-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="db6c3-116">ランタイムは、呼び出しから返されるストリームのルックアップ キーとしてこの識別子を使用することも、`IHostAssemblyStore::ProvideAssembly`メソッド。</span><span class="sxs-lookup"><span data-stu-id="db6c3-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="db6c3-117">そのため、識別子は、アセンブリの要求とモジュールの要求も一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="db6c3-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db6c3-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="db6c3-118">Requirements</span></span>  
 <span data-ttu-id="db6c3-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6c3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db6c3-120">**ヘッダー:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="db6c3-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="db6c3-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="db6c3-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db6c3-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db6c3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6c3-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="db6c3-123">See also</span></span>

- [<span data-ttu-id="db6c3-124">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="db6c3-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="db6c3-125">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="db6c3-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="db6c3-126">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db6c3-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="db6c3-127">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db6c3-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="db6c3-128">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db6c3-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
