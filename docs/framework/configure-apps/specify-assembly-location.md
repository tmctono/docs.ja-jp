---
title: アセンブリの場所の指定
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: f7d09e315f2ccc7ecdcf22719ca6dce1ee1411b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186291"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="5caa1-102">アセンブリの場所の指定</span><span class="sxs-lookup"><span data-stu-id="5caa1-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="5caa1-103">アセンブリの場所を指定する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="5caa1-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="5caa1-104">使用して、 [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="5caa1-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="5caa1-105">使用して、 [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="5caa1-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="5caa1-106">使用することも、 [.NET Framework 構成ツール (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100))アセンブリの場所を指定したり、共通言語ランタイム アセンブリを探すために場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="5caa1-107">使用して、 \<codeBase > 要素</span><span class="sxs-lookup"><span data-stu-id="5caa1-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="5caa1-108">使用することができます、  **\<codeBase >** のみマシン構成またはパブリッシャー ポリシー ファイルでも、アセンブリのバージョンをリダイレクトする要素。</span><span class="sxs-lookup"><span data-stu-id="5caa1-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="5caa1-109">ランタイムを使用するアセンブリ バージョンの決定、バージョンを決定するファイルからコードの基本設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5caa1-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="5caa1-110">コード ベースが示されていない場合、ランタイムは、通常の方法でアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="5caa1-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="5caa1-111">詳細については、次を参照してください。[ランタイムがアセンブリを検索する方法](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="5caa1-112">次の例では、アセンブリの場所を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="5caa1-113">**バージョン**属性のすべての厳密な名前のアセンブリが必要ですが、アセンブリの厳密な名前が付いていない場合は省略されます。</span><span class="sxs-lookup"><span data-stu-id="5caa1-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="5caa1-114"> *\*\<CodeBase >** 要素が必要です、 *\*href*\*属性。</span><span class="sxs-lookup"><span data-stu-id="5caa1-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="5caa1-115">バージョン範囲を指定することはできません、  **\<codeBase >** 要素。</span><span class="sxs-lookup"><span data-stu-id="5caa1-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5caa1-116">厳密な名前ではないアセンブリのコード ベースのヒントを指定する場合、ヒントは、アプリケーション ベースまたはアプリケーション ベース ディレクトリのサブディレクトリにポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5caa1-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="5caa1-117">使用して、 \<probing > 要素</span><span class="sxs-lookup"><span data-stu-id="5caa1-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="5caa1-118">ランタイムが調査して、コード ベースを持たないアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="5caa1-119">プローブの詳細については、次を参照してください。[ランタイムがアセンブリを検索する方法](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="5caa1-120">使用することができます、 [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)ランタイムがアセンブリを検索するときに検索するサブディレクトリを指定するアプリケーション構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="5caa1-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="5caa1-121">次の例では、ランタイムが検索するディレクトリを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="5caa1-122">**PrivatePath**属性には、ランタイムがアセンブリを検索するディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5caa1-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="5caa1-123">アプリケーションが C:\Program \myapp にある場合は、ランタイムが C:\Program Files\MyApp\Bin、C:\Program Files\MyApp\Bin2\Subbin、および C:\Program Files\MyApp\Bin3 コード ベースが指定されていないアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="5caa1-124">指定したディレクトリ**privatePath**アプリケーション ベース ディレクトリのサブディレクトリにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5caa1-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5caa1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5caa1-125">See also</span></span>

- [<span data-ttu-id="5caa1-126">共通言語ランタイムのアセンブリ</span><span class="sxs-lookup"><span data-stu-id="5caa1-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="5caa1-127">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="5caa1-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="5caa1-128">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="5caa1-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="5caa1-129">構成ファイルを使用してアプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="5caa1-129">Configuring Apps by using Configuration Files</span></span>](index.md)
