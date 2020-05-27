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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006754"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="32e11-102">ModuleBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="32e11-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="32e11-103">参照されるモジュールとそれを含むアセンブリに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="32e11-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e11-104">構文</span><span class="sxs-lookup"><span data-stu-id="32e11-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="32e11-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="32e11-105">Members</span></span>  
  
|<span data-ttu-id="32e11-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="32e11-106">Member</span></span>|<span data-ttu-id="32e11-107">説明</span><span class="sxs-lookup"><span data-stu-id="32e11-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="32e11-108">参照先の `IStream` モジュールの読み込み元である[IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md)メソッドへの呼び出しによって返されるの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="32e11-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="32e11-109">参照されたモジュールを含むアセンブリの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="32e11-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="32e11-110">参照されているモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="32e11-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e11-111">コメント</span><span class="sxs-lookup"><span data-stu-id="32e11-111">Remarks</span></span>  
 <span data-ttu-id="32e11-112">`ModuleBindInfo`は、にパラメーターとして渡され `IHostAssemblyStore::ProvideModule` ます。</span><span class="sxs-lookup"><span data-stu-id="32e11-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="32e11-113">ホストは、一意の識別子 `dwAppDomainId` を共通言語ランタイム (CLR) に提供します。</span><span class="sxs-lookup"><span data-stu-id="32e11-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="32e11-114">[IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md)メソッドの呼び出しが返されると、ランタイムは識別子を使用して、の内容が `IStream` マップされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32e11-114">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="32e11-115">その場合、ランタイムはストリームを再マップするのではなく、既存のコピーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="32e11-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="32e11-116">ランタイムは、メソッドへの呼び出しから返されるストリームの参照キーとしても、この識別子を使用し `IHostAssemblyStore::ProvideAssembly` ます。</span><span class="sxs-lookup"><span data-stu-id="32e11-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="32e11-117">このため、識別子は、モジュール要求とアセンブリ要求に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="32e11-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e11-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="32e11-118">Requirements</span></span>  
 <span data-ttu-id="32e11-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32e11-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e11-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32e11-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="32e11-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="32e11-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32e11-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e11-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e11-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="32e11-123">See also</span></span>

- [<span data-ttu-id="32e11-124">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="32e11-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="32e11-125">AssemblyBindInfo 構造体</span><span class="sxs-lookup"><span data-stu-id="32e11-125">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="32e11-126">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32e11-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="32e11-127">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32e11-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="32e11-128">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32e11-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
