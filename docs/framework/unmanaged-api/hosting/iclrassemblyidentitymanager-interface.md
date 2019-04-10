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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b209e568b1e65ed785155d045cd48d1248672da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209802"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="8046f-102">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8046f-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="8046f-103">ホストとアセンブリの詳細については、共通言語ランタイム (CLR) 間の通信をサポートするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8046f-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8046f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-104">Methods</span></span>  
  
|<span data-ttu-id="8046f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-105">Method</span></span>|<span data-ttu-id="8046f-106">説明</span><span class="sxs-lookup"><span data-stu-id="8046f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8046f-107">GetBindingIdentityFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="8046f-108">指定したファイル パスにあるアセンブリのデータをバインドするアセンブリ id を取得します。</span><span class="sxs-lookup"><span data-stu-id="8046f-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="8046f-109">GetBindingIdentityFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="8046f-110">指定されたストリーム内のアセンブリの標準アセンブリの id データを取得します。</span><span class="sxs-lookup"><span data-stu-id="8046f-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="8046f-111">GetCLRAssemblyReferenceList メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="8046f-112">取得、 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)部分的なアセンブリ id の指定されたリストからのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="8046f-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="8046f-113">GetProbingAssembliesFromReference メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="8046f-114">取得、 [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)指定した id を持つアセンブリによって参照されるアセンブリ id の列挙子。</span><span class="sxs-lookup"><span data-stu-id="8046f-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="8046f-115">GetReferencedAssembliesFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="8046f-116">取得、 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)インスタンスを指定したファイル パスにあるアセンブリによって参照されるアセンブリの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8046f-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="8046f-117">GetReferencedAssembliesFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="8046f-118">ポインターを取得、`ICLRReferenceAssemblyEnum`指定されたストリーム内のアセンブリによって参照されるアセンブリのアセンブリの id データを格納しているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8046f-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="8046f-119">IsStronglyNamed メソッド</span><span class="sxs-lookup"><span data-stu-id="8046f-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="8046f-120">指定したアセンブリが厳密な名前かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8046f-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8046f-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="8046f-121">Remarks</span></span>  
 <span data-ttu-id="8046f-122">使用`ICLRAssemblyIdentityManager`のインスタンスを取得`ICLRAssemblyReferenceList`とアセンブリ id を列挙します。</span><span class="sxs-lookup"><span data-stu-id="8046f-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8046f-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="8046f-123">Requirements</span></span>  
 <span data-ttu-id="8046f-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8046f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8046f-125">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8046f-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8046f-126">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8046f-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8046f-127">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8046f-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8046f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="8046f-128">See also</span></span>

- [<span data-ttu-id="8046f-129">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8046f-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8046f-130">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8046f-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="8046f-131">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8046f-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
