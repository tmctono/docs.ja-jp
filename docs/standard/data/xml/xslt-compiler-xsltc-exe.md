---
title: XSLT コンパイラ (xsltc.exe)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 729e6caa36ed8c2f6e77153f8d8ae356513b0603
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956989"
---
# <a name="xslt-compiler-xsltcexe"></a><span data-ttu-id="1fa85-102">XSLT コンパイラ (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="1fa85-102">XSLT Compiler (xsltc.exe)</span></span>
<span data-ttu-id="1fa85-103">XSLT コンパイラ (xsltc.exe) は、XSLT スタイル シートをコンパイルしてアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="1fa85-104">コンパイルしたスタイル シートを <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> メソッドに直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-104">The compiled style sheet can then be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1fa85-105">xsltc.exe を使用して署名があるアセンブリを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1fa85-105">You cannot generate signed assemblies with xsltc.exe.</span></span>  
  
 <span data-ttu-id="1fa85-106">xsltc.exe ツールは Visual Studio に付属しています。</span><span class="sxs-lookup"><span data-stu-id="1fa85-106">The xsltc.exe tool is included with Visual Studio.</span></span> <span data-ttu-id="1fa85-107">詳細については、[Visual Studio のダウンロード](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa85-107">For more information, see the [Visual Studio Downloads](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa85-108">構文</span><span class="sxs-lookup"><span data-stu-id="1fa85-108">Syntax</span></span>  
  
```console  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a><span data-ttu-id="1fa85-109">引数</span><span class="sxs-lookup"><span data-stu-id="1fa85-109">Argument</span></span>  
  
|<span data-ttu-id="1fa85-110">引数</span><span class="sxs-lookup"><span data-stu-id="1fa85-110">Argument</span></span>|<span data-ttu-id="1fa85-111">説明</span><span class="sxs-lookup"><span data-stu-id="1fa85-111">Description</span></span>|  
|--------------|-----------------|  
|`sourceFile`|<span data-ttu-id="1fa85-112">スタイル シートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-112">Specifies the name of the style sheet.</span></span> <span data-ttu-id="1fa85-113">スタイル シートはローカル ファイルであるか、イントラネット上に置かれていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="1fa85-113">The style sheet must be a local file or be located on the intranet.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="1fa85-114">および</span><span class="sxs-lookup"><span data-stu-id="1fa85-114">Options</span></span>  
  
|<span data-ttu-id="1fa85-115">OPTION</span><span class="sxs-lookup"><span data-stu-id="1fa85-115">Option</span></span>|<span data-ttu-id="1fa85-116">説明</span><span class="sxs-lookup"><span data-stu-id="1fa85-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1fa85-117">`/c[lass]:` `name`</span><span class="sxs-lookup"><span data-stu-id="1fa85-117">`/c[lass]:` `name`</span></span>|<span data-ttu-id="1fa85-118">以降のスタイル シートのクラス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-118">Specifies the name of the class for the following style sheet.</span></span> <span data-ttu-id="1fa85-119">クラス名には完全修飾名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-119">The class name can be fully qualified.</span></span><br /><br /> <span data-ttu-id="1fa85-120">既定のクラス名は、スタイル シートの名前です。</span><span class="sxs-lookup"><span data-stu-id="1fa85-120">The class name defaults to the name of the style sheet.</span></span> <span data-ttu-id="1fa85-121">たとえば、スタイル シート customers.xsl をコンパイルした場合、既定のクラス名は customers になります。</span><span class="sxs-lookup"><span data-stu-id="1fa85-121">For example, if the style sheet customers.xsl is compiled, the default class name is customers.</span></span>|  
|<span data-ttu-id="1fa85-122">`/debug[`+&#124;-`]`</span><span class="sxs-lookup"><span data-stu-id="1fa85-122">`/debug[`+&#124;-`]`</span></span>|<span data-ttu-id="1fa85-123">デバッグ情報を生成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-123">Specifies whether to generate debugging information.</span></span><br /><br /> <span data-ttu-id="1fa85-124">`+` または `/debug` を指定すると、コンパイラによりデバッグ情報が生成され、プログラム データベース (PDB) ファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-124">Specifying `+` or `/debug`, causes the compiler to generate debugging information and put it in a program database (PDB) file.</span></span> <span data-ttu-id="1fa85-125">生成される PDB ファイルの名前は `assemblyName`.pdb です。</span><span class="sxs-lookup"><span data-stu-id="1fa85-125">The name of the generated PDB file is `assemblyName`.pdb.</span></span><br /><br /> <span data-ttu-id="1fa85-126">`-` を指定しない場合、`/debug` の指定が有効となります。これを指定した場合、デバッグ情報は作成されません。</span><span class="sxs-lookup"><span data-stu-id="1fa85-126">Specifying `-`, which is in effect if you do not specify `/debug`, causes no debug information to be created.</span></span> <span data-ttu-id="1fa85-127">製品版のアセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-127">A retail assembly is generated.</span></span> <span data-ttu-id="1fa85-128">**注:** デバッグ モードでコンパイルすると、XSLT のパフォーマンスが大きな影響を受けることがあります。</span><span class="sxs-lookup"><span data-stu-id="1fa85-128">**Note:**  Compiling in debug mode can affect XSLT performance significantly.</span></span>|  
|`/help`|<span data-ttu-id="1fa85-129">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-129">Displays command syntax and options for the tool.</span></span>|  
|`/nologo`|<span data-ttu-id="1fa85-130">コンパイラの著作権メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="1fa85-130">Suppresses the compiler copyright message from displaying.</span></span>|  
|<span data-ttu-id="1fa85-131">`/platform:` `string`</span><span class="sxs-lookup"><span data-stu-id="1fa85-131">`/platform:` `string`</span></span>|<span data-ttu-id="1fa85-132">アセンブリを実行できるプラットフォームを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-132">Specifies the platforms that the assembly can be run on.</span></span> <span data-ttu-id="1fa85-133">次に、有効なプラットフォームの値を示します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-133">The following describes the valid platform values:</span></span><br /><br /> <span data-ttu-id="1fa85-134">`x86` : 32 ビット x86 互換共通言語ランタイムにより実行できるように、アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1fa85-134">`x86` compiles your assembly to be run by the 32-bit, x86-compatible common language runtime</span></span><br /><br /> <span data-ttu-id="1fa85-135">`x64` : AMD64 または EM64T 命令セットをサポートするコンピューターで 64 ビット共通言語ランタイムにより実行できるように、アセンブリをコンパイルします</span><span class="sxs-lookup"><span data-stu-id="1fa85-135">`x64` compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span><br /><br /> <span data-ttu-id="1fa85-136">Itanium は、Itanium プロセッサを搭載したコンピューターで 64 ビット共通言語ランタイムにより実行できるように、アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1fa85-136">Itanium compiles your assembly to be run by the 64-bit common language runtime on a computer that has an Itanium processor.</span></span><br /><br /> <span data-ttu-id="1fa85-137">`anycpu` : 任意のプラットフォーム上で実行できるように、アセンブリをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1fa85-137">`anycpu` compiles your assembly to run on any platform.</span></span> <span data-ttu-id="1fa85-138">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1fa85-138">This is the default.</span></span>|  
|<span data-ttu-id="1fa85-139">`/out:` `assemblyName`</span><span class="sxs-lookup"><span data-stu-id="1fa85-139">`/out:` `assemblyName`</span></span>|<span data-ttu-id="1fa85-140">出力となるアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-140">Specifies the name of the assembly that is output.</span></span> <span data-ttu-id="1fa85-141">複数のスタイル シートが存在している場合、既定のアセンブリ名はメインのスタイル シートか最初のスタイル シートの名前になります。</span><span class="sxs-lookup"><span data-stu-id="1fa85-141">The assembly name defaults to the name of the main style sheet or the first style sheet if multiple style sheets are present.</span></span><br /><br /> <span data-ttu-id="1fa85-142">スタイル シートにスクリプトが含まれている場合、スクリプトは別のアセンブリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-142">If the style sheet contains scripts, the scripts are saved to a separate assembly.</span></span> <span data-ttu-id="1fa85-143">スクリプト アセンブリ名は、メインのアセンブリ名から生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-143">Script assembly names are generated from the main assembly name.</span></span> <span data-ttu-id="1fa85-144">たとえば、アセンブリ名を CustOrders.dll と指定した場合、最初のスクリプト アセンブリは CustOrders_Script1.dll という名前になります。</span><span class="sxs-lookup"><span data-stu-id="1fa85-144">For example, if you specified CustOrders.dll for your assembly name, the first script assembly is named CustOrders_Script1.dll.</span></span>|  
|<span data-ttu-id="1fa85-145">`/settings:` `document+-, script+-, DTD+-,`</span><span class="sxs-lookup"><span data-stu-id="1fa85-145">`/settings:` `document+-, script+-, DTD+-,`</span></span>|<span data-ttu-id="1fa85-146">スタイル シートで `document()` 関数、XSLT スクリプト、またはドキュメント型定義 (DTD) を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-146">Specifies whether to allow `document()` functions, XSLT script, or document type definition (DTD) in the style sheet.</span></span><br /><br /> <span data-ttu-id="1fa85-147">既定では、DTD、`document()` 関数、スクリプトのサポートは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="1fa85-147">The default behavior disables support for DTD, the `document()` function and scripting.</span></span>|  
|<span data-ttu-id="1fa85-148">`@` `file`</span><span class="sxs-lookup"><span data-stu-id="1fa85-148">`@` `file`</span></span>|<span data-ttu-id="1fa85-149">コンパイラ オプションを含むファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-149">Lets you specify a file that contains the compiler options.</span></span>|  
|`?`|<span data-ttu-id="1fa85-150">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="1fa85-150">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fa85-151">コメント</span><span class="sxs-lookup"><span data-stu-id="1fa85-151">Remarks</span></span>  
 <span data-ttu-id="1fa85-152">XSLT ソリューションは、複数のスタイル シート モジュールで構成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-152">XSLT solutions can consist of multiple style sheet modules.</span></span> <span data-ttu-id="1fa85-153">xsltc.exe ツールを使用して、スタイル シートからアセンブリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-153">The xsltc.exe tool generates assemblies from style sheets.</span></span> <span data-ttu-id="1fa85-154">このアセンブリを <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> メソッドに直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-154">The assemblies can then be passed into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1fa85-155">XSLT の配置シナリオによっては、これによってパフォーマンス コストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-155">This can help decrease performance costs in some XSLT deployment scenarios.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fa85-156">アプリケーションには、コンパイル済みのアセンブリも参照として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa85-156">You must also include the compiled assembly as a reference in your application.</span></span>  
  
 <span data-ttu-id="1fa85-157">xsltc.exe ツールでは、クラス名 (`/class:`*name*) やアセンブリ名 (`/out:`*assemblyName*) が検証されません。</span><span class="sxs-lookup"><span data-stu-id="1fa85-157">The xsltc.exe tool does not validate the class (`/class:`*name*) or assembly (`/out:`*assemblyName*) names.</span></span> <span data-ttu-id="1fa85-158">名前が無効である場合、共通言語ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-158">Errors are thrown by the common language runtime if the names are not valid.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1fa85-159">使用例</span><span class="sxs-lookup"><span data-stu-id="1fa85-159">Examples</span></span>  
 <span data-ttu-id="1fa85-160">次のコマンドを実行すると、スタイル シートがコンパイルされ、booksort.dll という名前のアセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-160">The following command compiles the style sheet and creates an assembly named booksort.dll.</span></span>  
  
```console  
xsltc booksort.xsl  
```  
  
 <span data-ttu-id="1fa85-161">次のコマンドを実行すると、スタイル シートがコンパイルされ、booksort.dll という名前のアセンブリと booksort.pdb という名前の PDB ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-161">The following command compiles the style sheet and creates an assembly and PDB file that are named booksort.dll and booksort.pdb respectively.</span></span>  
  
```console  
xsltc booksort.xsl /debug  
```  
  
 <span data-ttu-id="1fa85-162">次のコマンドを実行すると、msxsl:script 要素を含むスタイル シートがコンパイルされ、calc.dll および calc_Script1.dll という 2 つのアセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-162">The following command compiles a style sheet that contains an msxsl:script element and creates two assemblies named calc.dll and calc_Script1.dll.</span></span>  
  
```console  
xsltc /settings:script+ calc.xsl  
```  
  
 <span data-ttu-id="1fa85-163">次のコマンドを実行すると、DTD 処理とスタイルのサポートが有効になり、myTest.dll および myTest_Script1.dll という 2 つのアセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-163">The following command enables DTD processing and script support and creates two assemblies named myTest.dll and myTest_Script1.dll.</span></span>  
  
```console  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 <span data-ttu-id="1fa85-164">次のコマンドを実行すると、2 つのスタイル シート モジュールがコンパイルされ、booksort.dll という名前のアセンブリが 1 つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa85-164">The following command compiles two style sheet modules and creates a single assembly named booksort.dll.</span></span>  
  
```console  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fa85-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fa85-165">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="1fa85-166">2 つのオブジェクトが等しいかどうかをテストする方法アセンブリを使用して XSLT 変換を実行する</span><span class="sxs-lookup"><span data-stu-id="1fa85-166">How to: Perform an XSLT Transformation by Using an Assembly</span></span>](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)
- [<span data-ttu-id="1fa85-167">XSLT 変換</span><span class="sxs-lookup"><span data-stu-id="1fa85-167">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
