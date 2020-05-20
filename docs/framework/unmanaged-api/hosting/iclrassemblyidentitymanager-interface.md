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
ms.openlocfilehash: f06c8228d5eb850c0d5ff94d12be03d7fb75023b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615918"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="67fdd-102">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67fdd-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="67fdd-103">ホストと、アセンブリに関する共通言語ランタイム (CLR) 間の通信をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67fdd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-104">Methods</span></span>  
  
|<span data-ttu-id="67fdd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-105">Method</span></span>|<span data-ttu-id="67fdd-106">説明</span><span class="sxs-lookup"><span data-stu-id="67fdd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67fdd-107">GetBindingIdentityFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-107">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="67fdd-108">指定したファイルパスにあるアセンブリのアセンブリ id バインドデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="67fdd-109">GetBindingIdentityFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-109">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="67fdd-110">指定したストリーム内のアセンブリの正規アセンブリ id データを取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="67fdd-111">GetCLRAssemblyReferenceList メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="67fdd-112">指定された部分アセンブリ id のリストから[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-112">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="67fdd-113">GetProbingAssembliesFromReference メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="67fdd-114">指定した id を持つアセンブリによって参照されるアセンブリ id の[ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-114">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="67fdd-115">GetReferencedAssembliesFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="67fdd-116">指定したファイルパスにあるアセンブリによって参照されるアセンブリのリストを含む[ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-116">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="67fdd-117">GetReferencedAssembliesFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-117">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="67fdd-118">`ICLRReferenceAssemblyEnum`指定したストリーム内のアセンブリによって参照されるアセンブリのアセンブリ id データを格納しているオブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="67fdd-119">IsStronglyNamed メソッド</span><span class="sxs-lookup"><span data-stu-id="67fdd-119">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="67fdd-120">指定したアセンブリに厳密な名前が付けられているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67fdd-121">解説</span><span class="sxs-lookup"><span data-stu-id="67fdd-121">Remarks</span></span>  
 <span data-ttu-id="67fdd-122">`ICLRAssemblyIdentityManager`のインスタンスを取得し `ICLRAssemblyReferenceList` 、アセンブリ id を列挙するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="67fdd-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67fdd-123">要件</span><span class="sxs-lookup"><span data-stu-id="67fdd-123">Requirements</span></span>  
 <span data-ttu-id="67fdd-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67fdd-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67fdd-125">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67fdd-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67fdd-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="67fdd-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67fdd-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67fdd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67fdd-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="67fdd-128">See also</span></span>

- [<span data-ttu-id="67fdd-129">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67fdd-129">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="67fdd-130">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67fdd-130">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="67fdd-131">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67fdd-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
