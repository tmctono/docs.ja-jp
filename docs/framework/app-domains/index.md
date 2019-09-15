---
title: アプリケーション ドメインとアセンブリを使用したプログラミング
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4f0c2ad1290a7f9cf8d0c43c504a3e0a9628b86
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971923"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="5f989-102">アプリケーション ドメインとアセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="5f989-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="5f989-103">Microsoft Internet Explorer、ASP.NET、Windows シェルなどのホストは、共通言語ランタイムをプロセスに読み込み、そのプロセス内で[アプリケーション ドメイン](../../../docs/framework/app-domains/application-domains.md)を作成します。その後 .NET Framework アプリケーションを実行するときに、そのアプリケーション ドメインにユーザー コードを読み込んでコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f989-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="5f989-104">通常、アプリケーション ドメインの作成およびそれらのドメインへのアセンブリの読み込みはランタイム ホストが実行するため、考慮する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5f989-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="5f989-105">しかし、共通言語ランタイムをホストするアプリケーションを作成する場合、プログラムによってアンロードされるツールまたはコードを作成する場合、または実行時にアンロードおよび再読み込みできるプラグ可能なコンポーネントを作成する場合は、独自のアプリケーション ドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f989-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="5f989-106">ランタイム ホストを作成しない場合でも、このセクションにある、アプリケーション ドメインとアプリケーション ドメインに読み込まれたアセンブリをどのように使用するかという説明は重要です。</span><span class="sxs-lookup"><span data-stu-id="5f989-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f989-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5f989-107">In This Section</span></span>  
 [<span data-ttu-id="5f989-108">アプリケーション ドメインとアセンブリに関する方法のトピック</span><span class="sxs-lookup"><span data-stu-id="5f989-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="5f989-109">アプリケーション ドメインとアセンブリを使用したプログラミングの概念に関するドキュメントに用意されているすべての方法トピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="5f989-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="5f989-110">アプリケーション ドメインの使用</span><span class="sxs-lookup"><span data-stu-id="5f989-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="5f989-111">アプリケーション ドメインを作成、構成、および使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f989-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="5f989-112">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="5f989-112">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
 <span data-ttu-id="5f989-113">アセンブリを作成し、署名し、その属性を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5f989-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f989-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f989-114">Related Sections</span></span>  
 [<span data-ttu-id="5f989-115">動的メソッドおよびアセンブリの出力</span><span class="sxs-lookup"><span data-stu-id="5f989-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="5f989-116">動的アセンブリの作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5f989-116">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="5f989-117">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="5f989-117">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
 <span data-ttu-id="5f989-118">アセンブリの概念的な概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="5f989-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="5f989-119">アプリケーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="5f989-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="5f989-120">アプリケーション ドメインの概念的な概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="5f989-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="5f989-121">リフレクションの概要</span><span class="sxs-lookup"><span data-stu-id="5f989-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="5f989-122">**Reflection** クラスを使用して、アセンブリに関する情報を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5f989-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
