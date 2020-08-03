---
title: '方法: CodeDOM を使用して XML ドキュメント ファイルを作成する'
description: この詳細な例では、Code Document Object Model (CodeDOM) を使用して XML ドキュメント ファイルを作成するコードを生成する方法について確認します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
ms.openlocfilehash: f905b996910c6cfbc62378cc4cd6bb8c0e0e6fd4
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865152"
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="8a16f-103">方法: CodeDOM を使用して XML ドキュメント ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="8a16f-103">How to: Create an XML documentation file using CodeDOM</span></span>

<span data-ttu-id="8a16f-104">CodeDOM を利用し、XML ドキュメントを生成するコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a16f-104">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="8a16f-105">XML ドキュメント コメントを含む CodeDOM グラフを作成する、コードを生成する、XML 文書出力を作成するコンパイラ オプションでその生成されたコードをコンパイルするというプロセスが行われます。</span><span class="sxs-lookup"><span data-stu-id="8a16f-105">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
## <a name="create-a-codedom-graph"></a><span data-ttu-id="8a16f-106">CodeDOM グラフの作成</span><span class="sxs-lookup"><span data-stu-id="8a16f-106">Create a CodeDOM graph</span></span>
  
1. <span data-ttu-id="8a16f-107">サンプル アプリケーションの CodeDOM グラフを含む <xref:System.CodeDom.CodeCompileUnit> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8a16f-107">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2. <span data-ttu-id="8a16f-108"><xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> コンストラクターを使用します。このとき、`docComment` パラメーターを `true` に設定し、XML ドキュメント コメントの要素とテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a16f-108">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="8a16f-109">CodeCompileUnit からコードを生成する</span><span class="sxs-lookup"><span data-stu-id="8a16f-109">Generate the code from the CodeCompileUnit</span></span>
  
1. <span data-ttu-id="8a16f-110"><xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> メソッドを使用し、コードを生成し、コンパイルするソース ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a16f-110">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="8a16f-111">コードをコンパイルしてドキュメント ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="8a16f-111">Compile the code and generate the documentation file</span></span>
  
1. <span data-ttu-id="8a16f-112"><xref:System.CodeDom.Compiler.CompilerParameters> オブジェクトの <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> プロパティに **/doc** コンパイラ オプションを追加し、オブジェクトを <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> メソッドに渡し、コードのコンパイル時に XML ドキュメント ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a16f-112">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="8a16f-113">例</span><span class="sxs-lookup"><span data-stu-id="8a16f-113">Example</span></span>

<span data-ttu-id="8a16f-114">次のコード例では、ドキュメント コメントのある CodeDOM グラフを作成し、グラフからコード ファイルを生成し、ファイルをコンパイルし、関連 XML ドキュメント ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a16f-114">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 <span data-ttu-id="8a16f-115">このコード例では、*HelloWorldDoc.xml* ファイルで次の XML ドキュメントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8a16f-115">The code example creates the following XML documentation in the *HelloWorldDoc.xml* file.</span></span>  
  
```xml  
<?xml version="1.0" ?>
<doc>  
  <assembly>  
    <name>HelloWorld</name>
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.
      </summary>
      <seealso cref="M:Samples.Class1.Main" />
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.
        <para>Add a new paragraph to the description.</para>
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compile-permissions"></a><span data-ttu-id="8a16f-116">コンパイルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8a16f-116">Compile permissions</span></span>
  
<span data-ttu-id="8a16f-117">このコード サンプルを正しく実行するには、`FullTrust` アクセス許可を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a16f-117">This code example requires the `FullTrust` permission set to execute successfully.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a16f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a16f-118">See also</span></span>

- [<span data-ttu-id="8a16f-119">XML の使用によるコードのドキュメントの作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a16f-119">Document your code with XML (Visual Basic)</span></span>](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="8a16f-120">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="8a16f-120">XML documentation comments</span></span>](../../csharp/programming-guide/xmldoc/index.md)
- [<span data-ttu-id="8a16f-121">XML ドキュメント (C++)</span><span class="sxs-lookup"><span data-stu-id="8a16f-121">XML documentation (C++)</span></span>](/cpp/ide/xml-documentation-visual-cpp)
