---
title: アセンブリの場所の指定
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646032"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="b4354-102">アセンブリの場所の指定</span><span class="sxs-lookup"><span data-stu-id="b4354-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="b4354-103">アセンブリの場所を指定するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b4354-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="b4354-104">[\<コードベース>要素を](./file-schema/runtime/codebase-element.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="b4354-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="b4354-105">[\<プローブ>要素を](./file-schema/runtime/probing-element.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="b4354-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="b4354-106">.NET Framework[構成ツール (Mscorcfg.msc) を](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100))使用して、アセンブリの場所を指定したり、共通言語ランタイムがアセンブリを調査する場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4354-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="b4354-107">\<コードベース>要素の使用</span><span class="sxs-lookup"><span data-stu-id="b4354-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="b4354-108">\*\* \<codeBase>\*\* 要素は、アセンブリのバージョンをリダイレクトするコンピューター構成または発行者ポリシー ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4354-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="b4354-109">ランタイムは、使用するアセンブリ のバージョンを決定するときに、バージョンを決定するファイルからコード ベースの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="b4354-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="b4354-110">コード ベースが指定されていない場合、ランタイムは通常の方法でアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="b4354-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="b4354-111">詳細については、「[ランタイムがアセンブリを検索する方法](../deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4354-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="b4354-112">アセンブリの場所を指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="b4354-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="b4354-113">**バージョン**属性は、厳密な名前を持つアセンブリすべてに必要ですが、厳密な名前を持たないアセンブリでは省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4354-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="b4354-114">\*\* \<codeBase>\*\* 要素には**href**属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="b4354-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="b4354-115">\*\* \<codeBase>\*\* 要素でバージョン範囲を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4354-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4354-116">厳密な名前を持たないアセンブリにコード ベース ヒントを指定する場合、ヒントはアプリケーション ベースまたはアプリケーション ベース ディレクトリのサブディレクトリを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4354-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="b4354-117">プローブ>\<要素の使用</span><span class="sxs-lookup"><span data-stu-id="b4354-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="b4354-118">ランタイムは、プローブによってコード ベースを持たないアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="b4354-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="b4354-119">プローブの詳細については、「[ランタイムがアセンブリを検索する方法](../deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4354-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="b4354-120">アプリケーション構成ファイルの[\<プローブ>](./file-schema/runtime/probing-element.md)要素を使用して、ランタイムがアセンブリを検索するときに検索するサブディレクトリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4354-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="b4354-121">ランタイムが検索するディレクトリを指定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="b4354-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b4354-122">**privatePath**属性には、ランタイムがアセンブリを検索するディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4354-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="b4354-123">アプリケーションが C:\Program Files\MyApp にある場合、ランタイムは C:\プログラム ファイル\MyApp\Bin、C:\プログラム ファイル\MyApp\Bin2\Subbin、および C:\プログラム ファイル\MyApp\Bin3 でコード ベースを指定していないアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="b4354-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="b4354-124">**privatePath**で指定するディレクトリは、アプリケーションベースディレクトリのサブディレクトリでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b4354-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4354-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4354-125">See also</span></span>

- [<span data-ttu-id="b4354-126">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="b4354-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="b4354-127">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="b4354-127">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="b4354-128">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="b4354-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="b4354-129">構成ファイルを使用してアプリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b4354-129">Configuring Apps by using Configuration Files</span></span>](index.md)
