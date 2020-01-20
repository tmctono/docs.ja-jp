---
title: '方法: 厳密な名前でアセンブリに署名する'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 64f3a51b29a7116c736fea0e76465a4a73c640c2
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738767"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="f0592-102">方法: 厳密な名前でアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="f0592-102">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="f0592-103">.NET Core では厳密な名前のアセンブリがサポートされており、.NET Core ライブラリ内のすべてのアセンブリは署名されていますが、ほとんどのサードパーティ アセンブリには厳密な名前は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f0592-103">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="f0592-104">詳細については、GitHub の「[厳密な名前の署名](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0592-104">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="f0592-105">厳密な名前でアセンブリに署名するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f0592-105">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="f0592-106">Visual Studio でプロジェクトの **[プロパティ]** ダイアログ ボックスにある **[署名]** タブを使用する。</span><span class="sxs-lookup"><span data-stu-id="f0592-106">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="f0592-107">これは、厳密な名前でアセンブリに署名するための最も簡単で便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="f0592-107">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="f0592-108">[アセンブリ リンカー (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) を使用して、.NET Framework のコード モジュール ( *.netmodule* ファイル) をキー ファイルにリンクする。</span><span class="sxs-lookup"><span data-stu-id="f0592-108">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="f0592-109">アセンブリ属性を使用して、厳密な名前情報をコードに挿入する。</span><span class="sxs-lookup"><span data-stu-id="f0592-109">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="f0592-110">使用するキー ファイルが配置されている場所に応じて、 <xref:System.Reflection.AssemblyKeyFileAttribute> または <xref:System.Reflection.AssemblyKeyNameAttribute> 属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0592-110">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="f0592-111">コンパイラ オプションを使用する。</span><span class="sxs-lookup"><span data-stu-id="f0592-111">By using compiler options.</span></span>  
  
 <span data-ttu-id="f0592-112">厳密な名前でアセンブリに署名するには、暗号キー ペアが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0592-112">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="f0592-113">キー ペアの作成の詳細については、「[方法:公開キーと秘密キーのキー ペアを作成する](create-public-private-key-pair.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0592-113">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="f0592-114">Visual Studio を使用してアセンブリを作成し、厳密な名前でそのアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="f0592-114">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="f0592-115">**ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0592-115">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="f0592-116">**[署名]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0592-116">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="f0592-117">**[アセンブリの署名]** ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0592-117">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="f0592-118">**[厳密な名前のキー ファイルを選択してください]** ボックスで **[参照]** をクリックし、キー ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="f0592-118">In the **Choose a strong name key file** box, choose **Browse**, and then navigate to the key file.</span></span> <span data-ttu-id="f0592-119">新しいキー ファイルを作成するには、 **[新規作成]** を選択し、 **[厳密な名前キーの作成]** ダイアログ ボックスでその名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0592-119">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0592-120">[アセンブリの遅延署名](delay-sign.md)を行うには、公開キー ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0592-120">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="f0592-121">アセンブリ リンカーを使用してアセンブリを作成し、厳密な名前でそのアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="f0592-121">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="f0592-122">[Visual Studio 用開発者コマンド プロンプト](../../framework/tools/developer-command-prompt-for-vs.md)で次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f0592-122">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="f0592-123">**al** **/out:** \<*assemblyName*>  *\<moduleName>* **/keyfile:** \<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="f0592-123">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="f0592-124">この場合、</span><span class="sxs-lookup"><span data-stu-id="f0592-124">Where:</span></span>  

- <span data-ttu-id="f0592-125">*assemblyName*は、アセンブリ リンカーが生成する、厳密な名前で署名されたアセンブリ ( *.dll* ファイルまたは *.exe* ファイル) の名前です。</span><span class="sxs-lookup"><span data-stu-id="f0592-125">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="f0592-126">*moduleName* は、1 つ以上の型を含む、.NET Framework コード モジュール ( *.netmodule* ファイル) の名前です。</span><span class="sxs-lookup"><span data-stu-id="f0592-126">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="f0592-127">C# または Visual Basic で `/target:module` スイッチを使ってコードをコンパイルすることにより、 *.netmodule* ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f0592-127">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="f0592-128">*keyfileName* は、キー ペアを格納しているコンテナーまたはファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="f0592-128">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="f0592-129">アセンブリ リンカーは、現在のディレクトリとの関連で相対パスを解釈します。</span><span class="sxs-lookup"><span data-stu-id="f0592-129">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="f0592-130">次の例では、キー ファイル *sgKey.snk* を使用して、厳密な名前でアセンブリ *MyAssembly.dll* に署名します。</span><span class="sxs-lookup"><span data-stu-id="f0592-130">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="f0592-131">このツールの詳細については、「 [アセンブリ リカー](../../framework/tools/al-exe-assembly-linker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0592-131">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="f0592-132">属性を使用して厳密な名前でアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="f0592-132">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="f0592-133"><xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> または <xref:System.Reflection.AssemblyKeyNameAttribute> 属性をソース コード ファイルに追加して、厳密な名前でアセンブリに署名するときに使用するキー ペアを格納するファイルまたはコンテナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0592-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
   
2. <span data-ttu-id="f0592-134">ソース コード ファイルを通常どおりにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f0592-134">Compile the source code file normally.</span></span>  
   
   > [!NOTE]
   > <span data-ttu-id="f0592-135">C# および Visual Basic コンパイラは、ソース コードで <xref:System.Reflection.AssemblyKeyFileAttribute> または <xref:System.Reflection.AssemblyKeyNameAttribute> 属性が見つかった場合、コンパイラ警告を発行します (CS1699 と BC41008)。</span><span class="sxs-lookup"><span data-stu-id="f0592-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="f0592-136">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="f0592-136">You can ignore the warnings.</span></span>  

<span data-ttu-id="f0592-137">次の例は、*keyfile.snk* という名前のキー ファイルを指定して、<xref:System.Reflection.AssemblyKeyFileAttribute> 属性を使用します。このキー ファイルは、アセンブリがコンパイルされるディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="f0592-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk*, which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="f0592-138">ソース ファイルのコンパイル時に、アセンブリに遅延署名することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0592-138">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="f0592-139">詳細については、「[アセンブリへの遅延署名](delay-sign.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0592-139">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="f0592-140">コンパイラを使用して厳密な名前でアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="f0592-140">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="f0592-141">C# と Visual Basic では `/keyfile` または `/delaysign` コンパイラ オプションを使用し、C++ では `/KEYFILE` または `/DELAYSIGN` リンカー オプションを使用して、ソース コード ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f0592-141">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="f0592-142">オプション名の後に、コロンと、キー ファイルの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0592-142">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="f0592-143">コマンド ライン コンパイラを使用する場合は、ソース コード ファイルを格納するディレクトリにキー ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f0592-143">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="f0592-144">遅延署名については、「[アセンブリへの遅延署名](delay-sign.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0592-144">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="f0592-145">次の例は、C# コンパイラを使用し、アセンブリ *UtilityLibrary.dll* にキー ファイル *sgKey.snk* を使用して厳密な名前で署名します。</span><span class="sxs-lookup"><span data-stu-id="f0592-145">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="f0592-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0592-146">See also</span></span>

- [<span data-ttu-id="f0592-147">厳密な名前付きアセンブリの作成と使用</span><span class="sxs-lookup"><span data-stu-id="f0592-147">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="f0592-148">方法: 公開キーと秘密キーのキー ペアを作成する</span><span class="sxs-lookup"><span data-stu-id="f0592-148">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="f0592-149">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="f0592-149">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="f0592-150">アセンブリへの遅延署名</span><span class="sxs-lookup"><span data-stu-id="f0592-150">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="f0592-151">アセンブリおよびマニフェストへの署名の管理</span><span class="sxs-lookup"><span data-stu-id="f0592-151">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- <span data-ttu-id="f0592-152">[[署名] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/signing-page-project-designer)</span><span class="sxs-lookup"><span data-stu-id="f0592-152">[Signing page, Project Designer](/visualstudio/ide/reference/signing-page-project-designer)</span></span>
