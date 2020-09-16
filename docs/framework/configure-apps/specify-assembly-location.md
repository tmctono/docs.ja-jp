---
title: アセンブリの場所の指定
description: XML 構成ファイルで codeBase 要素またはプローブ要素を使用して、.NET でアセンブリの場所を指定する方法を参照してください。
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 3b24ff99eee9027d507ef89ca855162f221f826a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555121"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="d8e41-103">アセンブリの場所の指定</span><span class="sxs-lookup"><span data-stu-id="d8e41-103">Specifying an Assembly's Location</span></span>
<span data-ttu-id="d8e41-104">アセンブリの場所を指定するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d8e41-104">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="d8e41-105">要素を使用し [\<codeBase>](./file-schema/runtime/codebase-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-105">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="d8e41-106">要素を使用し [\<probing>](./file-schema/runtime/probing-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-106">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="d8e41-107">また、 [.NET Framework 構成ツール (mscorcfg.msc)](/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) を使用して、アセンブリの場所を指定したり、共通言語ランタイムがアセンブリをプローブする場所を指定したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-107">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="d8e41-108">要素の使用 \<codeBase></span><span class="sxs-lookup"><span data-stu-id="d8e41-108">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="d8e41-109">要素は、 **\<codeBase>** アセンブリのバージョンをリダイレクトするコンピューターの構成ファイルまたは発行者ポリシーファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-109">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="d8e41-110">使用するアセンブリバージョンをランタイムが決定すると、バージョンを決定するファイルのコードベース設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-110">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="d8e41-111">コードベースが指定されていない場合、ランタイムは通常の方法でアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="d8e41-111">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="d8e41-112">詳細については、「 [ランタイムがアセンブリを検索する方法](../deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e41-112">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="d8e41-113">アセンブリの場所を指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="d8e41-113">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="d8e41-114">**Version**属性は、厳密な名前を持つすべてのアセンブリに必要ですが、厳密な名前ではないアセンブリでは省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e41-114">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="d8e41-115">要素には **\<codeBase>** **href** 属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8e41-115">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="d8e41-116">要素でバージョン範囲を指定することはできません **\<codeBase>** 。</span><span class="sxs-lookup"><span data-stu-id="d8e41-116">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8e41-117">厳密な名前が付けられていないアセンブリのコードベースヒントを指定する場合、ヒントはアプリケーションベースディレクトリのアプリケーションベースまたはサブディレクトリをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e41-117">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="d8e41-118">要素の使用 \<probing></span><span class="sxs-lookup"><span data-stu-id="d8e41-118">Using the \<probing> Element</span></span>  
 <span data-ttu-id="d8e41-119">実行時に、プローブによってコードベースのないアセンブリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-119">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="d8e41-120">プローブの詳細については、「 [ランタイムがアセンブリを検索する方法](../deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e41-120">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="d8e41-121">アプリケーション構成ファイルの要素を使用して、 [\<probing>](./file-schema/runtime/probing-element.md) ランタイムがアセンブリを検索するときに検索する必要のあるサブディレクトリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8e41-121">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="d8e41-122">次の例は、ランタイムが検索するディレクトリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8e41-122">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d8e41-123">**PrivatePath**属性には、ランタイムがアセンブリを検索するディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8e41-123">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="d8e41-124">アプリケーションが C:\Program Files\MyApp に配置されている場合、ランタイムは C:\Program Files\MyApp\Bin、C:\Program Files\MyApp\Bin2\Subbin、および C:\Program Files\MyApp\Bin3. でコードベースを指定していないアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="d8e41-124">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="d8e41-125">**PrivatePath**に指定されたディレクトリは、アプリケーションのベースディレクトリのサブディレクトリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8e41-125">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e41-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8e41-126">See also</span></span>

- [<span data-ttu-id="d8e41-127">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="d8e41-127">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="d8e41-128">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="d8e41-128">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="d8e41-129">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="d8e41-129">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="d8e41-130">構成ファイルを使用してアプリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d8e41-130">Configuring Apps by using Configuration Files</span></span>](index.md)
