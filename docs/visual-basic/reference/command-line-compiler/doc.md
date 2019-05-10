---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: c3bff4e44ddee1c4dfb6ab366464ad54e991b595
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624272"
---
# <a name="-doc"></a><span data-ttu-id="6c517-102">-doc</span><span class="sxs-lookup"><span data-stu-id="6c517-102">-doc</span></span>
<span data-ttu-id="6c517-103">ドキュメント コメントを XML ファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="6c517-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c517-104">構文</span><span class="sxs-lookup"><span data-stu-id="6c517-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c517-105">引数</span><span class="sxs-lookup"><span data-stu-id="6c517-105">Arguments</span></span>  
  
|<span data-ttu-id="6c517-106">用語</span><span class="sxs-lookup"><span data-stu-id="6c517-106">Term</span></span>|<span data-ttu-id="6c517-107">定義</span><span class="sxs-lookup"><span data-stu-id="6c517-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="6c517-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6c517-108">`+` &#124; `-`</span></span>|<span data-ttu-id="6c517-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6c517-109">Optional.</span></span> <span data-ttu-id="6c517-110">+、または単に `-doc` を指定すると、コンパイラによってドキュメント情報が生成され、XML ファイル内に置かれます。</span><span class="sxs-lookup"><span data-stu-id="6c517-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="6c517-111">`-` を指定することは `-doc` を指定しないことと同じで、この場合ドキュメント情報は作成されません。</span><span class="sxs-lookup"><span data-stu-id="6c517-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="6c517-112">`-doc:` を使用する場合に、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="6c517-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="6c517-113">出力の XML ファイルを指定します。これにはコンパイルのソース コード ファイルからのコメントが入力されます。</span><span class="sxs-lookup"><span data-stu-id="6c517-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="6c517-114">ファイル名に空白が含まれている場合は、名前を引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6c517-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c517-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c517-115">Remarks</span></span>  
 <span data-ttu-id="6c517-116">`-doc` オプションでは、コンパイラにドキュメント コメントを含む XML ファイルを生成させるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="6c517-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="6c517-117">`-doc:file` 構文を使用する場合、`file` パラメーターによって XML ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c517-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="6c517-118">`-doc` または `-doc+` を使用する場合、コンパイラは、コンパイラが作成中の実行可能ファイルまたはライブラリから XML ファイルの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c517-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="6c517-119">`-doc-` を使用する場合、または `-doc` オプションを指定しない場合、コンパイラは XML ファイルを作成しません。</span><span class="sxs-lookup"><span data-stu-id="6c517-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="6c517-120">ソース コード ファイルで、ドキュメント コメントを次の定義の前に置くことができます。</span><span class="sxs-lookup"><span data-stu-id="6c517-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
- <span data-ttu-id="6c517-121">[クラス](../../../visual-basic/language-reference/statements/class-statement.md)や[インターフェイス](../../../visual-basic/language-reference/statements/interface-statement.md)などのユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6c517-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
- <span data-ttu-id="6c517-122">フィールド、[イベント](../../../visual-basic/language-reference/statements/event-statement.md)、[プロパティ](../../../visual-basic/language-reference/statements/property-statement.md)、[関数](../../../visual-basic/language-reference/statements/function-statement.md)、[サブルーチン](../../../visual-basic/language-reference/statements/sub-statement.md)などのメンバー。</span><span class="sxs-lookup"><span data-stu-id="6c517-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="6c517-123">Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) 機能で生成された XML ファイルを使用するには、XML ファイルの名前をサポートするアセンブリの名前と同じにします。</span><span class="sxs-lookup"><span data-stu-id="6c517-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="6c517-124">Visual Studio プロジェクトでアセンブリが参照されたときに .xml ファイルがうまく見つかるようにするために、XML ファイルがアセンブリと同じディレクトリにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c517-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="6c517-125">IntelliSense をプロジェクト内のコード、またはプロジェクトに参照されるプロジェクト内のコードに対して動作させるために、XML ドキュメント ファイルは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="6c517-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="6c517-126">`/target:module` を使用してコンパイルしない限り、XML ファイルにはタグ `<assembly></assembly>` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c517-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="6c517-127">これらのタグでは、コンパイルの出力ファイルに向けたアセンブリ マニフェストを含むファイルの名前が指定されます。</span><span class="sxs-lookup"><span data-stu-id="6c517-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="6c517-128">コード内のコメントからドキュメントを生成する方法については、「[XML のコメント用タグ](../../../visual-basic/language-reference/xmldoc/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c517-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="6c517-129">Visual Studio 統合開発環境で -doc を設定するには</span><span class="sxs-lookup"><span data-stu-id="6c517-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6c517-130">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c517-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6c517-131">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c517-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6c517-132">2.**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c517-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6c517-133">3.**[XML ドキュメント ファイルを生成する]** ボックスに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6c517-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6c517-134">例</span><span class="sxs-lookup"><span data-stu-id="6c517-134">Example</span></span>  
 <span data-ttu-id="6c517-135">サンプルについては、「[XML の使用によるコードのドキュメントの作成](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c517-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c517-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c517-136">See also</span></span>

- [<span data-ttu-id="6c517-137">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="6c517-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6c517-138">XML の使用によるコードのドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="6c517-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
