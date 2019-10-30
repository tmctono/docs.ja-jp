---
title: ICLRAssemblyIdentityManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: 26de2ebf1364981d8b8f1fb38c8fa1045191114f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126619"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="aac37-102">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aac37-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="aac37-103">ホストと、アセンブリに関する共通言語ランタイム (CLR) 間の通信をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="aac37-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aac37-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-104">Methods</span></span>  
  
|<span data-ttu-id="aac37-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-105">Method</span></span>|<span data-ttu-id="aac37-106">説明</span><span class="sxs-lookup"><span data-stu-id="aac37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aac37-107">GetBindingIdentityFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="aac37-108">指定したファイルパスにあるアセンブリのアセンブリ id バインドデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="aac37-109">GetBindingIdentityFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="aac37-110">指定したストリーム内のアセンブリの正規アセンブリ id データを取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="aac37-111">GetCLRAssemblyReferenceList メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="aac37-112">指定された部分アセンブリ id のリストから[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="aac37-113">GetProbingAssembliesFromReference メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="aac37-114">指定した id を持つアセンブリによって参照されるアセンブリ id の[ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="aac37-115">GetReferencedAssembliesFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="aac37-116">指定したファイルパスにあるアセンブリによって参照されるアセンブリのリストを含む[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="aac37-117">GetReferencedAssembliesFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="aac37-118">指定したストリーム内のアセンブリによって参照されるアセンブリのアセンブリ id データを格納している `ICLRReferenceAssemblyEnum` オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="aac37-119">IsStronglyNamed メソッド</span><span class="sxs-lookup"><span data-stu-id="aac37-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="aac37-120">指定したアセンブリに厳密な名前が付けられているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aac37-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aac37-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="aac37-121">Remarks</span></span>  
 <span data-ttu-id="aac37-122">`ICLRAssemblyIdentityManager` を使用して `ICLRAssemblyReferenceList` のインスタンスを取得し、アセンブリ id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="aac37-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aac37-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="aac37-123">Requirements</span></span>  
 <span data-ttu-id="aac37-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aac37-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aac37-125">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aac37-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aac37-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="aac37-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aac37-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac37-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac37-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="aac37-128">See also</span></span>

- [<span data-ttu-id="aac37-129">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aac37-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="aac37-130">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aac37-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="aac37-131">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aac37-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
