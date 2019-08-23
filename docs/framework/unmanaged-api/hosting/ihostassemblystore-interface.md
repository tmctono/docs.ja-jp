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
ms.openlocfilehash: f881440b2e93745723bd090cfbab0286dcd0a4e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937869"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="da5e8-102">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da5e8-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="da5e8-103">共通言語ランタイム (CLR) とは独立して、ホストがアセンブリとモジュールを読み込むことができるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="da5e8-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da5e8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="da5e8-104">Methods</span></span>  
  
|<span data-ttu-id="da5e8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="da5e8-105">Method</span></span>|<span data-ttu-id="da5e8-106">説明</span><span class="sxs-lookup"><span data-stu-id="da5e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da5e8-107">ProvideAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="da5e8-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="da5e8-108">[IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)の呼び出しから返された[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)によって参照されていないアセンブリへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="da5e8-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="da5e8-109">ProvideModule メソッド</span><span class="sxs-lookup"><span data-stu-id="da5e8-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="da5e8-110">アセンブリ内のモジュール、またはリンクされた (埋め込まれていない) リソースファイル内のモジュールを解決します。</span><span class="sxs-lookup"><span data-stu-id="da5e8-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da5e8-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="da5e8-111">Remarks</span></span>  
 <span data-ttu-id="da5e8-112">`IHostAssemblyStore`ホストがアセンブリ id に基づいてアセンブリを効率的に読み込む方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="da5e8-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="da5e8-113">ホストは、バイトを直接`IStream`指し示すインスタンスを返すことによって、アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="da5e8-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="da5e8-114">CLR は、初期化時にを呼び`IHostAssemblyStore`出す`IHostAssemblyManager::GetNonHostAssemblyStores`ことによってホストが実装されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="da5e8-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="da5e8-115">これにより、ホストは、たとえば、ユーザーアセンブリへのバインドを制御できますが、ランタイムに依存して .NET Framework アセンブリにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="da5e8-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da5e8-116">の`IHostAssemblyStore`実装を提供する場合、ホストはから`ICLRAssemblyReferenceList` `IHostAssemblyManager::GetNonHostStoreAssemblies`返されたによって参照されていないすべてのアセンブリを解決するための目的を指定します。</span><span class="sxs-lookup"><span data-stu-id="da5e8-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da5e8-117">.NET Framework バージョン2.0 では、[ネイティブイメージジェネレーター (ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)ユーティリティによって提供されるアセンブリのネイティブイメージをホストが読み込む方法は提供されていません。</span><span class="sxs-lookup"><span data-stu-id="da5e8-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da5e8-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="da5e8-118">Requirements</span></span>  
 <span data-ttu-id="da5e8-119">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da5e8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da5e8-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="da5e8-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da5e8-121">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="da5e8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da5e8-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da5e8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5e8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="da5e8-123">See also</span></span>

- [<span data-ttu-id="da5e8-124">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da5e8-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="da5e8-125">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da5e8-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="da5e8-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da5e8-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
