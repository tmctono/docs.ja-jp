---
title: IHostAssemblyStore インターフェイス
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930040"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="67a23-102">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67a23-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="67a23-103">アセンブリおよび共通言語ランタイム (CLR) とは無関係にモジュールの読み込みにホストできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="67a23-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67a23-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="67a23-104">Methods</span></span>  
  
|<span data-ttu-id="67a23-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="67a23-105">Method</span></span>|<span data-ttu-id="67a23-106">説明</span><span class="sxs-lookup"><span data-stu-id="67a23-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67a23-107">ProvideAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="67a23-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="67a23-108">によって参照されているアセンブリへの参照を取得、 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)への呼び出しから返された[ihostassemblymanager::getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="67a23-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="67a23-109">ProvideModule メソッド</span><span class="sxs-lookup"><span data-stu-id="67a23-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="67a23-110">アセンブリまたはリンク (組み込まれていない) リソース ファイル内のモジュールを解決します。</span><span class="sxs-lookup"><span data-stu-id="67a23-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67a23-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="67a23-111">Remarks</span></span>  
 <span data-ttu-id="67a23-112">`IHostAssemblyStore` ホストがアセンブリ id に基づいた効率的にアセンブリを読み込む方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="67a23-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="67a23-113">ホストでは、アセンブリを読み込んで返すことによって`IStream`バイトを直接ポイントするインスタンス。</span><span class="sxs-lookup"><span data-stu-id="67a23-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="67a23-114">CLR は、ホストが実装されているかどうかを決定します。`IHostAssemblyStore`呼び出して`IHostAssemblyManager::GetNonHostAssemblyStores`の初期化時にします。</span><span class="sxs-lookup"><span data-stu-id="67a23-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="67a23-115">これにより、ホスト、たとえば、.NET Framework アセンブリへのバインドをランタイムに依存するが、ユーザーのアセンブリへのバインディングを制御します。</span><span class="sxs-lookup"><span data-stu-id="67a23-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67a23-116">実装を提供するために`IHostAssemblyStore`、ホストによって参照されていないすべてのアセンブリを解決するのにはその目的を指定します、`ICLRAssemblyReferenceList`から返された`IHostAssemblyManager::GetNonHostStoreAssemblies`します。</span><span class="sxs-lookup"><span data-stu-id="67a23-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67a23-117">によって提供される、.NET Framework version 2.0 が、ホスト、アセンブリのネイティブ イメージを読み込むための手段を提供しない、[ネイティブ イメージ ジェネレーター (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="67a23-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67a23-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="67a23-118">Requirements</span></span>  
 <span data-ttu-id="67a23-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67a23-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a23-120">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67a23-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67a23-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="67a23-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67a23-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a23-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a23-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="67a23-123">See also</span></span>

- [<span data-ttu-id="67a23-124">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67a23-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="67a23-125">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67a23-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="67a23-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67a23-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
