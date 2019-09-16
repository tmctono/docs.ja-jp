---
title: アセンブリの配置
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 829aa80169319b67a8cc5ee39fee9214cd4fcbce
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971640"
---
# <a name="assembly-placement"></a><span data-ttu-id="43af5-102">アセンブリの配置</span><span class="sxs-lookup"><span data-stu-id="43af5-102">Assembly Placement</span></span>
<span data-ttu-id="43af5-103">多くの .NET Framework アプリケーションの場合、アプリケーションを構成するアセンブリは、そのアプリケーションのディレクトリ、アプリケーション ディレクトリのサブディレクトリ、またはグローバル アセンブリ キャッシュ (アセンブリが共有されている場合) に配置します。</span><span class="sxs-lookup"><span data-stu-id="43af5-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="43af5-104">構成ファイルの [\<codeBase> エレメント](../../framework/configure-apps/file-schema/runtime/codebase-element.md)を使用すると、共通言語ランタイムがアセンブリを検索する場所をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="43af5-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="43af5-105">アセンブリが厳密な名前を持たない場合、[\<codeBase> エレメント](../../framework/configure-apps/file-schema/runtime/codebase-element.md)を使用して指定できる場所は、そのアプリケーションのディレクトリまたはサブディレクトリに制限されます。</span><span class="sxs-lookup"><span data-stu-id="43af5-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="43af5-106">アセンブリが厳密な名前を持つ場合は、[\<codeBase> エレメント](../../framework/configure-apps/file-schema/runtime/codebase-element.md)を使用してコンピューターまたはネットワーク上の任意の場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="43af5-106">If the assembly has a strong name, the [\<codeBase> Element](../../framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="43af5-107">また、アンマネージ コード アプリケーションや COM 相互運用アプリケーションで使用するアセンブリを検索する場所についても似たような規則が適用されます。アセンブリを複数のアプリケーションで共有する場合、そのアセンブリの検索場所はグローバル アセンブリ キャッシュになります。</span><span class="sxs-lookup"><span data-stu-id="43af5-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="43af5-108">アンマネージ コードで使用するアセンブリは、型ライブラリとしてエクスポートし、登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43af5-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="43af5-109">COM 相互運用で使用するアセンブリは、カタログに登録する必要がありますが、場合によっては、この登録が自動的に行われることもあります。</span><span class="sxs-lookup"><span data-stu-id="43af5-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43af5-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="43af5-110">See also</span></span>

- [<span data-ttu-id="43af5-111">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="43af5-111">How the Runtime Locates Assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="43af5-112">アプリの構成</span><span class="sxs-lookup"><span data-stu-id="43af5-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="43af5-113">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="43af5-113">Interoperating with unmanaged code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="43af5-114">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="43af5-114">Assemblies in .NET</span></span>](index.md)
