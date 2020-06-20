---
title: '方法: DEVPATH を使用してアセンブリを指定する'
description: XML コンピューター構成ファイルと DEVPATH 環境変数を使用して、共有アセンブリが .NET の多くのアプリケーションで正しく動作することをテストします。
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 50b61eedddabd660b1834565a61738f460ae9ff9
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105372"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="0fa23-103">方法: DEVPATH を使用してアセンブリを指定する</span><span class="sxs-lookup"><span data-stu-id="0fa23-103">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="0fa23-104">開発者は、ビルドしている共有アセンブリが複数のアプリケーションで正しく動作することを確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fa23-104">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="0fa23-105">開発サイクル中にアセンブリをグローバルアセンブリキャッシュに継続的に配置するのではなく、開発者はアセンブリのビルド出力ディレクトリを指す DEVPATH 環境変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0fa23-105">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="0fa23-106">たとえば、MySharedAssembly という名前の共有アセンブリを作成し、出力ディレクトリを C:\MySharedAssembly\Debug. にするとします。</span><span class="sxs-lookup"><span data-stu-id="0fa23-106">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="0fa23-107">C:\MySharedAssembly\Debug を DEVPATH 変数に配置できます。</span><span class="sxs-lookup"><span data-stu-id="0fa23-107">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="0fa23-108">次 [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) に、マシン構成ファイルで要素を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa23-108">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="0fa23-109">この要素は、アセンブリを検索するために DEVPATH を使用するように共通言語ランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="0fa23-109">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="0fa23-110">共有アセンブリは、ランタイムによって検出可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa23-110">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="0fa23-111">アセンブリ参照を解決するためのプライベートディレクトリを指定するには、「[アセンブリの場所の指定](specify-assembly-location.md)」で説明されているように、構成ファイル内の[ \<codeBase> 要素](./file-schema/runtime/codebase-element.md)または[ \<probing> 要素](./file-schema/runtime/probing-element.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0fa23-111">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="0fa23-112">また、アセンブリをアプリケーションディレクトリのサブディレクトリに配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fa23-112">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="0fa23-113">詳細については、「[ランタイムがアセンブリを検索する方法](../deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fa23-113">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fa23-114">これは高度な機能であり、開発のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="0fa23-114">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="0fa23-115">次の例は、DEVPATH 環境変数によって指定されたディレクトリ内のアセンブリをランタイムが検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fa23-115">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fa23-116">例</span><span class="sxs-lookup"><span data-stu-id="0fa23-116">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="0fa23-117">この設定の既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="0fa23-117">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fa23-118">この設定は、開発時にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="0fa23-118">Use this setting only at development time.</span></span> <span data-ttu-id="0fa23-119">ランタイムは、DEVPATH で見つかった厳密な名前のアセンブリのバージョンをチェックしません。</span><span class="sxs-lookup"><span data-stu-id="0fa23-119">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="0fa23-120">単純に、最初に見つかったアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fa23-120">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa23-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fa23-121">See also</span></span>

- [<span data-ttu-id="0fa23-122">構成ファイルを使用してアプリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0fa23-122">Configuring Apps by using Configuration Files</span></span>](index.md)
