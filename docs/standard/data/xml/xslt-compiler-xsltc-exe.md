---
title: XSLT コンパイラ (xsltc.exe)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
ms.openlocfilehash: 18f351546699487316858198b705e970de4856c1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282611"
---
# <a name="xslt-compiler-xsltcexe"></a><span data-ttu-id="1f2bf-102">XSLT コンパイラ (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="1f2bf-102">XSLT Compiler (xsltc.exe)</span></span>
<span data-ttu-id="1f2bf-103">XSLT コンパイラ (xsltc.exe) は、XSLT スタイル シートをコンパイルしてアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="1f2bf-104">コンパイルしたスタイル シートを <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> メソッドに直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-104">The compiled style sheet can then be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1f2bf-105">xsltc.exe を使用して署名があるアセンブリを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-105">You cannot generate signed assemblies with xsltc.exe.</span></span>  
  
 <span data-ttu-id="1f2bf-106">xsltc.exe ツールは Visual Studio に付属しています。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-106">The xsltc.exe tool is included with Visual Studio.</span></span> <span data-ttu-id="1f2bf-107">詳細については、[Visual Studio のダウンロード](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-107">For more information, see the [Visual Studio Downloads](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f2bf-108">構文</span><span class="sxs-lookup"><span data-stu-id="1f2bf-108">Syntax</span></span>  
  
```console  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a><span data-ttu-id="1f2bf-109">引数</span><span class="sxs-lookup"><span data-stu-id="1f2bf-109">Argument</span></span>  
  
|<span data-ttu-id="1f2bf-110">引数</span><span class="sxs-lookup"><span data-stu-id="1f2bf-110">Argument</span></span>|<span data-ttu-id="1f2bf-111">説明</span><span class="sxs-lookup"><span data-stu-id="1f2bf-111">Description</span></span>|  
|--------------|-----------------|  
|`sourceFile`|<span data-ttu-id="1f2bf-112">スタイル シートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-112">Specifies the name of the style sheet.</span></span> <span data-ttu-id="1f2bf-113">スタイル シートはローカル ファイルであるか、イントラネット上に置かれていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-113">The style sheet must be a local file or be located on the intranet.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="1f2bf-114">オプション</span><span class="sxs-lookup"><span data-stu-id="1f2bf-114">Options</span></span>  
  
|<span data-ttu-id="1f2bf-115">オプション</span><span class="sxs-lookup"><span data-stu-id="1f2bf-115">Option</span></span>|<span data-ttu-id="1f2bf-116">説明</span><span class="sxs-lookup"><span data-stu-id="1f2bf-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1f2bf-117">`/c[lass]:` `name`</span><span class="sxs-lookup"><span data-stu-id="1f2bf-117">`/c[lass]:` `name`</span></span>|<span data-ttu-id="1f2bf-118">以降のスタイル シートのクラス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-118">Specifies the name of the class for the following style sheet.</span></span> <span data-ttu-id="1f2bf-119">クラス名には完全修飾名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-119">The class name can be fully qualified.</span></span><br /><br /> <span data-ttu-id="1f2bf-120">既定のクラス名は、スタイル シートの名前です。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-120">The class name defaults to the name of the style sheet.</span></span> <span data-ttu-id="1f2bf-121">たとえば、スタイル シート customers.xsl をコンパイルした場合、既定のクラス名は customers になります。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-121">For example, if the style sheet customers.xsl is compiled, the default class name is customers.</span></span>|  
|<span data-ttu-id="1f2bf-122">`/debug[`+&#124;-`]`</span><span class="sxs-lookup"><span data-stu-id="1f2bf-122">`/debug[`+&#124;-`]`</span></span>|<span data-ttu-id="1f2bf-123">デバッグ情報を生成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-123">Specifies whether to generate debugging information.</span></span><br /><br /> <span data-ttu-id="1f2bf-124">`+` または `/debug` を指定すると、コンパイラによりデバッグ情報が生成され、プログラム データベース (PDB) ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-124">Specifying `+` or `/debug`, causes the compiler to generate debugging information and put it in a program database (PDB) file.</span></span> <span data-ttu-id="1f2bf-125">生成される PDB ファイルの名前は `assemblyName`.pdb です。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-125">The name of the generated PDB file is `assemblyName`.pdb.</span></span><br /><br /> <span data-ttu-id="1f2bf-126">`-` を指定しない場合、`/debug` の指定が有効となります。これを指定した場合、デバッグ情報は作成されません。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-126">Specifying `-`, which is in effect if you do not specify `/debug`, causes no debug information to be created.</span></span> <span data-ttu-id="1f2bf-127">製品版のアセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-127">A retail assembly is generated.</span></span> <span data-ttu-id="1f2bf-128">**注:** デバッグ モードでコンパイルすると、XSLT のパフォーマンスが大きな影響を受けることがあります。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-128">**Note:**  Compiling in debug mode can affect XSLT performance significantly.</span></span>|  
|`/help`|<span data-ttu-id="1f2bf-129">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-129">Displays command syntax and options for the tool.</span></span>|  
|`/nologo`|<span data-ttu-id="1f2bf-130">コンパイラの著作権メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-130">Suppresses the compiler copyright message from displaying.</span></span>|  
|<span data-ttu-id="1f2bf-131">`/platform:` `string`</span><span class="sxs-lookup"><span data-stu-id="1f2bf-131">`/platform:` `string`</span></span>|<span data-ttu-id="1f2bf-132">アセンブリを実行できるプラットフォームを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-132">Specifies the platforms that the assembly can be run on.</span></span> <span data-ttu-id="1f2bf-133">次に、有効なプラットフォームの値を示します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-133">The following describes the valid platform values:</span></span><br /><br /> <span data-ttu-id="1f2bf-134">`x86` : 32 ビット x86 互換共通言語ランタイムにより実行できるように、アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-134">`x86` compiles your assembly to be run by the 32-bit, x86-compatible common language runtime</span></span><br /><br /> <span data-ttu-id="1f2bf-135">`x64` : AMD64 または EM64T 命令セットをサポートするコンピューターで 64 ビット共通言語ランタイムにより実行できるように、アセンブリをコンパイルします</span><span class="sxs-lookup"><span data-stu-id="1f2bf-135">`x64` compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span><br /><br /> <span data-ttu-id="1f2bf-136">Itanium は、Itanium プロセッサを搭載したコンピューターで 64 ビット共通言語ランタイムにより実行できるように、アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-136">Itanium compiles your assembly to be run by the 64-bit common language runtime on a computer that has an Itanium processor.</span></span><br /><br /> <span data-ttu-id="1f2bf-137">`anycpu` : 任意のプラットフォーム上で実行できるように、アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-137">`anycpu` compiles your assembly to run on any platform.</span></span> <span data-ttu-id="1f2bf-138">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-138">This is the default.</span></span>|  
|<span data-ttu-id="1f2bf-139">`/out:` `assemblyName`</span><span class="sxs-lookup"><span data-stu-id="1f2bf-139">`/out:` `assemblyName`</span></span>|<span data-ttu-id="1f2bf-140">出力となるアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-140">Specifies the name of the assembly that is output.</span></span> <span data-ttu-id="1f2bf-141">複数のスタイル シートが存在している場合、既定のアセンブリ名はメインのスタイル シートか最初のスタイル シートの名前になります。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-141">The assembly name defaults to the name of the main style sheet or the first style sheet if multiple style sheets are present.</span></span><br /><br /> <span data-ttu-id="1f2bf-142">スタイル シートにスクリプトが含まれている場合、スクリプトは別のアセンブリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-142">If the style sheet contains scripts, the scripts are saved to a separate assembly.</span></span> <span data-ttu-id="1f2bf-143">スクリプト アセンブリ名は、メインのアセンブリ名から生成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-143">Script assembly names are generated from the main assembly name.</span></span> <span data-ttu-id="1f2bf-144">たとえば、アセンブリ名を CustOrders.dll と指定した場合、最初のスクリプト アセンブリは CustOrders_Script1.dll という名前になります。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-144">For example, if you specified CustOrders.dll for your assembly name, the first script assembly is named CustOrders_Script1.dll.</span></span>|  
|<span data-ttu-id="1f2bf-145">`/settings:` `document+-, script+-, DTD+-,`</span><span class="sxs-lookup"><span data-stu-id="1f2bf-145">`/settings:` `document+-, script+-, DTD+-,`</span></span>|<span data-ttu-id="1f2bf-146">スタイル シートで `document()` 関数、XSLT スクリプト、またはドキュメント型定義 (DTD) を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-146">Specifies whether to allow `document()` functions, XSLT script, or document type definition (DTD) in the style sheet.</span></span><br /><br /> <span data-ttu-id="1f2bf-147">既定では、DTD、`document()` 関数、スクリプトのサポートは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-147">The default behavior disables support for DTD, the `document()` function and scripting.</span></span>|  
|<span data-ttu-id="1f2bf-148">`@` `file`</span><span class="sxs-lookup"><span data-stu-id="1f2bf-148">`@` `file`</span></span>|<span data-ttu-id="1f2bf-149">コンパイラ オプションを含むファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-149">Lets you specify a file that contains the compiler options.</span></span>|  
|`?`|<span data-ttu-id="1f2bf-150">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-150">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f2bf-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f2bf-151">Remarks</span></span>  
 <span data-ttu-id="1f2bf-152">XSLT ソリューションは、複数のスタイル シート モジュールで構成できます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-152">XSLT solutions can consist of multiple style sheet modules.</span></span> <span data-ttu-id="1f2bf-153">xsltc.exe ツールを使用して、スタイル シートからアセンブリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-153">The xsltc.exe tool generates assemblies from style sheets.</span></span> <span data-ttu-id="1f2bf-154">このアセンブリを <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> メソッドに直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-154">The assemblies can then be passed into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1f2bf-155">XSLT の配置シナリオによっては、これによってパフォーマンス コストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-155">This can help decrease performance costs in some XSLT deployment scenarios.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f2bf-156">アプリケーションには、コンパイル済みのアセンブリも参照として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-156">You must also include the compiled assembly as a reference in your application.</span></span>  
  
 <span data-ttu-id="1f2bf-157">xsltc.exe ツールでは、クラス名 (`/class:`*name*) やアセンブリ名 (`/out:`*assemblyName*) が検証されません。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-157">The xsltc.exe tool does not validate the class (`/class:`*name*) or assembly (`/out:`*assemblyName*) names.</span></span> <span data-ttu-id="1f2bf-158">名前が無効である場合、共通言語ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-158">Errors are thrown by the common language runtime if the names are not valid.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1f2bf-159">使用例</span><span class="sxs-lookup"><span data-stu-id="1f2bf-159">Examples</span></span>  
 <span data-ttu-id="1f2bf-160">次のコマンドを実行すると、スタイル シートがコンパイルされ、booksort.dll という名前のアセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-160">The following command compiles the style sheet and creates an assembly named booksort.dll.</span></span>  
  
```console  
xsltc booksort.xsl  
```  
  
 <span data-ttu-id="1f2bf-161">次のコマンドを実行すると、スタイル シートがコンパイルされ、booksort.dll という名前のアセンブリと booksort.pdb という名前の PDB ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-161">The following command compiles the style sheet and creates an assembly and PDB file that are named booksort.dll and booksort.pdb respectively.</span></span>  
  
```console  
xsltc booksort.xsl /debug  
```  
  
 <span data-ttu-id="1f2bf-162">次のコマンドを実行すると、msxsl:script 要素を含むスタイル シートがコンパイルされ、calc.dll および calc_Script1.dll という 2 つのアセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-162">The following command compiles a style sheet that contains an msxsl:script element and creates two assemblies named calc.dll and calc_Script1.dll.</span></span>  
  
```console  
xsltc /settings:script+ calc.xsl  
```  
  
 <span data-ttu-id="1f2bf-163">次のコマンドを実行すると、DTD 処理とスタイルのサポートが有効になり、myTest.dll および myTest_Script1.dll という 2 つのアセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-163">The following command enables DTD processing and script support and creates two assemblies named myTest.dll and myTest_Script1.dll.</span></span>  
  
```console  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 <span data-ttu-id="1f2bf-164">次のコマンドを実行すると、2 つのスタイル シート モジュールがコンパイルされ、booksort.dll という名前のアセンブリが 1 つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f2bf-164">The following command compiles two style sheet modules and creates a single assembly named booksort.dll.</span></span>  
  
```console  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f2bf-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f2bf-165">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="1f2bf-166">方法: アセンブリを使用して XSLT 変換を実行する</span><span class="sxs-lookup"><span data-stu-id="1f2bf-166">How to: Perform an XSLT Transformation by Using an Assembly</span></span>](how-to-perform-an-xslt-transformation-by-using-an-assembly.md)
- [<span data-ttu-id="1f2bf-167">XSLT 変換</span><span class="sxs-lookup"><span data-stu-id="1f2bf-167">XSLT Transformations</span></span>](xslt-transformations.md)
