---
title: ICorDebugProcess6::EnableVirtualModuleSplitting メソッド
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 8ad15d11ce81323b30434b3db98259a74a198f29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178572"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="f4826-102">ICorDebugProcess6::EnableVirtualModuleSplitting メソッド</span><span class="sxs-lookup"><span data-stu-id="f4826-102">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>
<span data-ttu-id="f4826-103">仮想モジュール分割を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="f4826-103">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4826-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4826-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4826-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4826-105">Parameters</span></span>  
 `enableSplitting`  
 <span data-ttu-id="f4826-106">仮想モジュール分割を有効にするには、`true`。無効にするには、`false`。</span><span class="sxs-lookup"><span data-stu-id="f4826-106">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4826-107">解説</span><span class="sxs-lookup"><span data-stu-id="f4826-107">Remarks</span></span>  
 <span data-ttu-id="f4826-108">仮想モジュールの分割により[、ICorDebug](icordebug-interface.md)はビルドプロセス中にマージされたモジュールを認識し、それらを 1 つの大きなモジュールではなく、個別のモジュールのグループとして表示します。</span><span class="sxs-lookup"><span data-stu-id="f4826-108">Virtual module splitting causes [ICorDebug](icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="f4826-109">これにより、以下に説明するさまざまな[ICorDebug](icordebug-interface.md)メソッドの動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f4826-109">Doing this changes the behavior of various [ICorDebug](icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4826-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4826-110">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="f4826-111">このメソッドを呼び出し、`enableSplitting` の値をいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="f4826-111">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="f4826-112">呼び出された時点で[の仮想モジュールの分割とアンマネージ デバッグ API](#APIs)セクションに記載されているメソッドの動作を変更する以外に[、ICorDebug](icordebug-interface.md)オブジェクトのステートフルな関数の変更は発生しません。</span><span class="sxs-lookup"><span data-stu-id="f4826-112">It does not cause any stateful functional changes in an [ICorDebug](icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="f4826-113">仮想モジュールを使用しても、これらのメソッドの呼び出し時にパフォーマンスの低下は発生しません。</span><span class="sxs-lookup"><span data-stu-id="f4826-113">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="f4826-114">さらに[、IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) API を正しく実装するために、仮想化されたメタデータのメモリ内キャッシュが重要になる場合があり、仮想モジュールの分割がオフになっていても、これらのキャッシュは保持される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4826-114">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="f4826-115">用語</span><span class="sxs-lookup"><span data-stu-id="f4826-115">Terminology</span></span>  
 <span data-ttu-id="f4826-116">仮想モジュール分割について説明する場合には、次の用語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4826-116">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="f4826-117">コンテナー モジュールまたはコンテナー</span><span class="sxs-lookup"><span data-stu-id="f4826-117">container modules, or containers</span></span>  
 <span data-ttu-id="f4826-118">集計モジュール。</span><span class="sxs-lookup"><span data-stu-id="f4826-118">The aggregate modules.</span></span>  
  
 <span data-ttu-id="f4826-119">サブモジュール、または仮想モジュール</span><span class="sxs-lookup"><span data-stu-id="f4826-119">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="f4826-120">コンテナー内にあるモジュール。</span><span class="sxs-lookup"><span data-stu-id="f4826-120">The modules found in a container.</span></span>  
  
 <span data-ttu-id="f4826-121">標準モジュール</span><span class="sxs-lookup"><span data-stu-id="f4826-121">regular modules</span></span>  
 <span data-ttu-id="f4826-122">ビルド時にマージされなかったモジュール。</span><span class="sxs-lookup"><span data-stu-id="f4826-122">Modules that were not merged at build time.</span></span> <span data-ttu-id="f4826-123">コンテナー モジュールでもサブモジュールでもありません。</span><span class="sxs-lookup"><span data-stu-id="f4826-123">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="f4826-124">コンテナー モジュールとサブモジュールは、どちらも ICorDebugModuleインターフェイス オブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="f4826-124">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="f4826-125">ただし、このセクションで説明しているように、インターフェイスの動作は>、\<各ケースで若干異なります。</span><span class="sxs-lookup"><span data-stu-id="f4826-125">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="f4826-126">モジュールとアセンブリ</span><span class="sxs-lookup"><span data-stu-id="f4826-126">Modules and assemblies</span></span>  
 <span data-ttu-id="f4826-127">アセンブリ マージ シナリオではマルチモジュール アセンブリはサポートされないため、モジュールとアセンブリの間には一対一リレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="f4826-127">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="f4826-128">各 ICorDebugModule オブジェクトには、コンテナー モジュールを表すかサブモジュールを表すかに関係なく、対応する ICorDebugAssembly オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="f4826-128">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="f4826-129">メソッドは[モジュール](icordebugmodule-getassembly-method.md)からアセンブリに変換されます。</span><span class="sxs-lookup"><span data-stu-id="f4826-129">The [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="f4826-130">他の方向にマップするには[、ICorDebugAssembly::列挙モジュール](icordebugassembly-enumeratemodules-method.md)メソッドは 1 つのモジュールのみを列挙します。</span><span class="sxs-lookup"><span data-stu-id="f4826-130">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="f4826-131">この場合、アセンブリとモジュールは緊密に結合されたペアとなるため、アセンブリとモジュールはほぼ同義の用語となります。</span><span class="sxs-lookup"><span data-stu-id="f4826-131">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="f4826-132">動作の違い</span><span class="sxs-lookup"><span data-stu-id="f4826-132">Behavioral differences</span></span>  
 <span data-ttu-id="f4826-133">コンテナー モジュールには、次の動作と特性があります。</span><span class="sxs-lookup"><span data-stu-id="f4826-133">Container modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="f4826-134">構成要素であるすべてのサブモジュールのメタデータはマージされます。</span><span class="sxs-lookup"><span data-stu-id="f4826-134">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
- <span data-ttu-id="f4826-135">型名は変形する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4826-135">Their type names may be mangled.</span></span>  
  
- <span data-ttu-id="f4826-136">メソッドは[、](icordebugmodule-getname-method.md)ディスク上のモジュールへのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-136">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
- <span data-ttu-id="f4826-137">メソッドは[、](icordebugmodule-getsize-method.md)そのイメージのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-137">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
- <span data-ttu-id="f4826-138">ICorDebugAssembly3.EnumerateContainedAssemblies メソッドは、サブモジュールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f4826-138">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
- <span data-ttu-id="f4826-139">ICorDebugAssembly3.GetContainerAssembly メソッドは、`S_FALSE` を返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-139">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="f4826-140">サブモジュールには、次の動作と特性があります。</span><span class="sxs-lookup"><span data-stu-id="f4826-140">Sub-modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="f4826-141">マージされた元のアセンブリのみに対応する削減されたメタデータのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="f4826-141">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
- <span data-ttu-id="f4826-142">メタデータ名は、変形しません。</span><span class="sxs-lookup"><span data-stu-id="f4826-142">The metadata names are not mangled.</span></span>  
  
- <span data-ttu-id="f4826-143">メタデータ トークンは、ビルド プロセスでマージされる前の元のアセンブリ内のトークンと一致することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="f4826-143">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
- <span data-ttu-id="f4826-144">メソッドは[、](icordebugmodule-getname-method.md)ファイル パスではなくアセンブリ名を返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-144">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
- <span data-ttu-id="f4826-145">メソッドは[、](icordebugmodule-getsize-method.md)元のマージされていないイメージ サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-145">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
- <span data-ttu-id="f4826-146">ICorDebugModule3.EnumerateContainedAssemblies メソッドは、`S_FALSE` を返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-146">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
- <span data-ttu-id="f4826-147">ICorDebugAssembly3.GetContainerAssembly メソッドは、格納しているモジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-147">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="f4826-148">モジュールから取得されるインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4826-148">Interfaces retrieved from modules</span></span>  
 <span data-ttu-id="f4826-149">さまざまなインターフェイスをモジュールから作成または取得できます。</span><span class="sxs-lookup"><span data-stu-id="f4826-149">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="f4826-150">たとえば、次のようなシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="f4826-150">Some of these include:</span></span>  
  
- <span data-ttu-id="f4826-151">[メソッドによって](icordebugmodule-getclassfromtoken-method.md)返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f4826-151">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
- <span data-ttu-id="f4826-152">[メソッドによって](icordebugmodule-getassembly-method.md)返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f4826-152">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="f4826-153">これらのオブジェクトは常に[ICorDebug](icordebug-interface.md)によってキャッシュされ、コンテナー モジュールまたはサブモジュールから作成またはクエリされたかどうかにかかわらず、同じポインター ID を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f4826-153">These objects are always cached by [ICorDebug](icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="f4826-154">サブモジュールは、独自のコピーを持つ個別のキャッシュではなく、これらのキャッシュされたオブジェクトのフィルター処理されたビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="f4826-154">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="f4826-155">仮想モジュール分割とアンマネージ デバッグ API</span><span class="sxs-lookup"><span data-stu-id="f4826-155">Virtual module splitting and the unmanaged debugging APIs</span></span>  
 <span data-ttu-id="f4826-156">次の表に、仮想モジュール分割がアンマネージ デバッグ API の他のメソッドの動作に影響する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f4826-156">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="f4826-157">Method</span><span class="sxs-lookup"><span data-stu-id="f4826-157">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="f4826-158">ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="f4826-158">ICorDebugFunction::GetModule</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="f4826-159">この関数が最初に定義されたサブモジュールを返します</span><span class="sxs-lookup"><span data-stu-id="f4826-159">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="f4826-160">この関数がマージされたコンテナー モジュールを返します</span><span class="sxs-lookup"><span data-stu-id="f4826-160">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="f4826-161">ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="f4826-161">ICorDebugClass::GetModule</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="f4826-162">このクラスが最初に定義されたサブモジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-162">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="f4826-163">このクラスがマージされたコンテナー モジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-163">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="f4826-164">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="f4826-164">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="f4826-165">読み込まれたコンテナー モジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-165">Returns the container module that was loaded.</span></span> <span data-ttu-id="f4826-166">サブモジュールは、この設定に関係なく、読み込みイベントを提供されません。</span><span class="sxs-lookup"><span data-stu-id="f4826-166">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="f4826-167">読み込まれたコンテナー モジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-167">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="f4826-168">ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="f4826-168">ICorDebugAppDomain::EnumerateAssemblies</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="f4826-169">サブアセンブリと標準アセンブリのリストを返します。コンテナー アセンブリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="f4826-169">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="f4826-170">**注:** コンテナー アセンブリにシンボルが見つからない場合、そのサブアセンブリは列挙されません。</span><span class="sxs-lookup"><span data-stu-id="f4826-170">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="f4826-171">いずれかの標準アセンブリにシンボルがない場合、列挙される場合と列挙されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4826-171">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="f4826-172">コンテナー アセンブリと標準アセンブリのリストを返します。サブアセンブリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="f4826-172">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="f4826-173">**注:** 通常のアセンブリにシンボルが見つからない場合は、列挙される場合と、列挙されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4826-173">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="f4826-174">[ICorデバッグコード::GetCode](icordebugcode-getcode-method.md) (ILコードのみを参照する場合)</span><span class="sxs-lookup"><span data-stu-id="f4826-174">[ICorDebugCode::GetCode](icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="f4826-175">マージ前のアセンブリ イメージ内で有効な IL を返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-175">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="f4826-176">具体的には、参照先の型が IL を含む仮想モジュールで定義されていない場合、インライン メタデータ トークンは正確に TypeRef または MemberRef トークンになります。</span><span class="sxs-lookup"><span data-stu-id="f4826-176">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="f4826-177">これらの型参照またはメンバー参照トークンは、対応する仮想 ICorDebugModule オブジェクトの[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)オブジェクトで検索できます。</span><span class="sxs-lookup"><span data-stu-id="f4826-177">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="f4826-178">マージ後のアセンブリ イメージ内の IL を返します。</span><span class="sxs-lookup"><span data-stu-id="f4826-178">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4826-179">必要条件</span><span class="sxs-lookup"><span data-stu-id="f4826-179">Requirements</span></span>  
 <span data-ttu-id="f4826-180">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4826-180">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4826-181">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4826-181">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4826-182">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4826-182">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4826-183">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4826-183">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4826-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4826-184">See also</span></span>

- [<span data-ttu-id="f4826-185">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4826-185">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="f4826-186">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4826-186">Debugging Interfaces</span></span>](debugging-interfaces.md)
