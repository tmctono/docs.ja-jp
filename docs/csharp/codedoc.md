---
title: XML コメントによるコードの文書化
description: XML ドキュメント コメントを含むコードを文書化し、コンパイル時に XML ドキュメント ファイルを生成する方法を説明します。
ms.date: 01/21/2020
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 91de11c610ea17999dabff6d0552de9440f532e6
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465300"
---
# <a name="document-your-code-with-xml-comments"></a><span data-ttu-id="c2f43-103">XML コメントを含むコードの文書化</span><span class="sxs-lookup"><span data-stu-id="c2f43-103">Document your code with XML comments</span></span>

<span data-ttu-id="c2f43-104">XML 文書化コメントは、ユーザー定義型またはユーザー定義メンバーの定義の上に追加する特殊なコメントです。</span><span class="sxs-lookup"><span data-stu-id="c2f43-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="c2f43-105">このコメントが特殊な理由は、コンパイル時にコンパイラで処理して、XML 文書化ファイルを生成できることです。</span><span class="sxs-lookup"><span data-stu-id="c2f43-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="c2f43-106">コンパイラによって生成された XML ファイルは、.NET アセンブリと共に配布できます。これにより、Visual Studio や他の IDE で、IntelliSense を使用して型やメンバーに関する概要情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-106">The compiler-generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="c2f43-107">さらに、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) のようなツールを使用して XML ファイルを実行し、API リファレンスの Web サイトを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="c2f43-108">XML 文書化コメントは、その他すべてのコメントと同じように、コンパイラによって無視されます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="c2f43-109">コンパイル時に XML ファイルを生成するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="c2f43-110">.NET Core を使用してコマンド ラインからアプリケーションを開発している場合は、.csproj プロジェクト ファイルの `<PropertyGroup>` セクションに `GenerateDocumentationFile` 要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-110">If you are developing an application with .NET Core from the command line, you can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="c2f43-111">また、[`DocumentationFile` 要素](/visualstudio/msbuild/common-msbuild-project-properties)を使用して、ドキュメント ファイルへのパスを直接指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-111">You can also specify the path to the documentation file directly using [`DocumentationFile` element](/visualstudio/msbuild/common-msbuild-project-properties).</span></span> <span data-ttu-id="c2f43-112">次の例では、プロジェクト ディレクトリの中に、アセンブリと同じルート ファイル名で XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-112">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

   <span data-ttu-id="c2f43-113">これは、次の指定と同じです。</span><span class="sxs-lookup"><span data-stu-id="c2f43-113">This is equivalent to the following:</span></span>

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- <span data-ttu-id="c2f43-114">Visual Studio を使用してアプリケーションを開発する場合は、プロジェクトを右クリックして、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="c2f43-115">プロパティ ダイアログ ボックスで、 **[ビルド]** タブをクリックし、 **[XML ドキュメント ファイル]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="c2f43-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="c2f43-116">コンパイラがファイルを書き込む場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="c2f43-117">コマンド ラインから .NET アプリケーションをコンパイルする場合は、コンパイル時に [-doc コンパイラ オプション](language-reference/compiler-options/doc-compiler-option.md)を追加してください。</span><span class="sxs-lookup"><span data-stu-id="c2f43-117">If you are compiling a .NET application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="c2f43-118">XML 文書化コメントには、3 つのスラッシュ (`///`) と、XML 形式のコメント本文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="c2f43-119">例:</span><span class="sxs-lookup"><span data-stu-id="c2f43-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="c2f43-120">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="c2f43-120">Walkthrough</span></span>

<span data-ttu-id="c2f43-121">基本的な数式ライブラリを文書化して、新しい開発者が理解/参加しやすく、サードパーティの開発者が使用しやすいものにする方法を確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="c2f43-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third-party developers to use.</span></span>

<span data-ttu-id="c2f43-122">シンプルな数式ライブラリのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="c2f43-123">サンプル ライブラリでは、4 つの主要な算術演算 (`add`、`subtract`、`multiply`、`divide`) が、`int` と `double` のデータ型でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c2f43-123">The sample library supports four major arithmetic operations (`add`, `subtract`, `multiply`, and `divide`) on `int` and `double` data types.</span></span>

<span data-ttu-id="c2f43-124">このライブラリを使用するがそのソース コードにはアクセスできないサード パーティの開発者向けに、コードから API リファレンス ドキュメントを作成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-124">Now you want to be able to create an API reference document from your code for third-party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="c2f43-125">前述のように、このために XML ドキュメント タグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="c2f43-126">そこで、C# コンパイラがサポートする標準の XML タグを紹介します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## \<summary>

<span data-ttu-id="c2f43-127">`<summary>` タグは、型またはメンバーに関する簡単な情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-127">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="c2f43-128">この例では、タグの使い方を示すために、このタグを `Math` クラス定義と最初の `Add` メソッドに追加しています。</span><span class="sxs-lookup"><span data-stu-id="c2f43-128">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="c2f43-129">コードのそれ以外の部分にも適用してかまいません。</span><span class="sxs-lookup"><span data-stu-id="c2f43-129">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="c2f43-130">`<summary>` は重要なタグです。IntelliSense や API のリファレンス ドキュメントでは、このタグの内容が型やメンバーに関する主要な情報源であるため、このタグを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c2f43-130">The `<summary>` tag is important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## \<remarks>

<span data-ttu-id="c2f43-131">`<remarks>` タグは、`<summary>` タグで提供される型やメンバーに関する情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-131">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="c2f43-132">この例では、このタグをクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-132">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## \<returns>

<span data-ttu-id="c2f43-133">`<returns>` タグは、メソッド宣言の戻り値を記述します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-133">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="c2f43-134">前と同様に、次の例は最初の `Add` メソッドに追加した `<returns>` タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2f43-134">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="c2f43-135">その他のメソッドにも同様に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-135">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## \<value>

<span data-ttu-id="c2f43-136">`<value>` タグは、プロパティに対して使用する点を除いて、`<returns>` タグと同じです。</span><span class="sxs-lookup"><span data-stu-id="c2f43-136">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="c2f43-137">`Math` ライブラリに `PI` という静的プロパティがある場合、このタグを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-137">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## \<example>

<span data-ttu-id="c2f43-138">`<example>` タグを使用して XML 文書化情報に例を挿入します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-138">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="c2f43-139">そのために、子 `<code>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-139">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="c2f43-140">`code` タグは、長い例で改行とインデント設定を維持します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-140">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## \<para>

<span data-ttu-id="c2f43-141">`<para>` タグは、親タグ内の内容を書式設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-141">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="c2f43-142">通常、`<para>` は `<remarks>` や `<returns>` などのタグの内側で使用して、テキストを段落に分割します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-142">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="c2f43-143">クラス定義で `<remarks>` タグの内容を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-143">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## \<c>

<span data-ttu-id="c2f43-144">これも書式設定のタグです。`<c>` タグは、テキストの一部をコードとしてマークするために使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-144">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="c2f43-145">`<code>` タグに似ていますが、インラインで記述する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-145">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="c2f43-146">タグの内容の一部として簡単なコード例を示すときに便利です。</span><span class="sxs-lookup"><span data-stu-id="c2f43-146">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="c2f43-147">`Math` クラスのドキュメントを更新してみましょう。</span><span class="sxs-lookup"><span data-stu-id="c2f43-147">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## \<exception>

<span data-ttu-id="c2f43-148">`<exception>` タグを使用すると、メソッドで特定の例外がスローされる可能性を開発者に知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-148">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="c2f43-149">`Math` ライブラリを見てみると、特定の条件が満たされた場合、両方の `Add` メソッドで例外がスローされることがわかります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-149">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="c2f43-150">一方、少しわかりにくいですが、`b`パラメーターが 0 の場合は整数の `Divide` メソッドでも例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-150">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="c2f43-151">ここで、このメソッドに例外のドキュメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-151">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="c2f43-152">`cref` 属性は、現在のコンパイル環境から使用できる例外の参照を表します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-152">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="c2f43-153">プロジェクトまたは参照されたアセンブリに定義されている任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-153">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="c2f43-154">コンパイラはその値を解決できない場合、警告を出します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-154">The compiler will issue a warning if its value cannot be resolved.</span></span>

## \<see>

<span data-ttu-id="c2f43-155">`<see>` タグでは、別のコード要素のドキュメント ページへのクリック可能なリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-155">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="c2f43-156">次の例では、2 つの `Add` メソッドの間にクリック可能なリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-156">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="c2f43-157">`cref` は**必須**属性です。現在のコンパイル環境から使用できる型またはその型のメンバーへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-157">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="c2f43-158">プロジェクトまたは参照されたアセンブリに定義されている任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-158">This can be any type defined in the project or a referenced assembly.</span></span>

## \<seealso>

<span data-ttu-id="c2f43-159">`<seealso>` タグは、`<see>` タグと同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-159">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="c2f43-160">唯一の違いは、このタグの内容が一般的に「関連項目」セクションに配置されることです。</span><span class="sxs-lookup"><span data-stu-id="c2f43-160">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="c2f43-161">ここで、`seealso` タグを整数の `Add` メソッドに追加して、クラス内の、整数パラメーターを受け取る他のメソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-161">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="c2f43-162">`cref` 属性は、現在のコンパイル環境から使用できる型またはその型のメンバーへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-162">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="c2f43-163">プロジェクトまたは参照されたアセンブリに定義されている任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-163">This can be any type defined in the project or a referenced assembly.</span></span>

## \<param>

<span data-ttu-id="c2f43-164">`<param>` タグは、メソッドのパラメーターを記述するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-164">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="c2f43-165">double 型の `Add` メソッドでの例を示します。タグで記述するパラメーターは**必須** `name`属性です。</span><span class="sxs-lookup"><span data-stu-id="c2f43-165">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## \<typeparam>

<span data-ttu-id="c2f43-166">`<typeparam>` タグは、`<param>` タグと同じように使用しますが、ジェネリック型またはメソッド宣言で、ジェネリック パラメーターを記述するために使用する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-166">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="c2f43-167">簡単なジェネリック メソッドを `Math` クラスに追加して、ある数量が別の数量より大きいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-167">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## \<paramref>

<span data-ttu-id="c2f43-168">場合によって、`<summary>` タグでメソッドの動作を記述している最中に、パラメーターを参照することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-168">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="c2f43-169">そのような場合は、`<paramref>` タグがまさに適しています。</span><span class="sxs-lookup"><span data-stu-id="c2f43-169">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="c2f43-170">double 型に基づく `Add` メソッドの概要を更新しましょう。</span><span class="sxs-lookup"><span data-stu-id="c2f43-170">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="c2f43-171">`<param>` タグと同様に、パラメーター名は**必須** `name` 属性で指定されます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-171">Like the `<param>` tag, the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## \<typeparamref>

<span data-ttu-id="c2f43-172">`<typeparamref>` タグは、`<paramref>` タグと同じように使用しますが、ジェネリック型またはメソッド宣言で、ジェネリック パラメーターを記述するために使用する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-172">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="c2f43-173">以前に作成した同じジェネリック メソッドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-173">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## \<list>

<span data-ttu-id="c2f43-174">`<list>` タグを使用して、ドキュメント情報を、順序指定済みリスト、順序指定されていないリスト、または表として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-174">You use the `<list>` tag to format documentation information as an ordered list, unordered list, or table.</span></span> <span data-ttu-id="c2f43-175">`Math` ライブラリがサポートするそれぞれの算術演算の順不同のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-175">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="c2f43-176">`type` 属性を `number` または `table` に変更することで、順序付きリストまたは表をそれぞれ作成できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-176">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

## \<inheritdoc>

<span data-ttu-id="c2f43-177">`<inheritdoc>` タグを使用して、基底クラス、インターフェイス、および同様のメソッドから XML コメントを継承できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-177">You can use the `<inheritdoc>` tag to inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="c2f43-178">これにより、重複する XML コメントの不要なコピーと貼り付けを行う必要がなくなり、XML コメントが自動的に同期されたままになります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-178">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>

[!code-csharp-interactive[InheritDoc Tag](~/samples/snippets/csharp/concepts/codedoc/inheritdoc-tag.cs)]

### <a name="put-it-all-together"></a><span data-ttu-id="c2f43-179">すべてをまとめた配置</span><span class="sxs-lookup"><span data-stu-id="c2f43-179">Put it all together</span></span>

<span data-ttu-id="c2f43-180">ここまで、チュートリアルに沿ってコードに必要なタグを適用し、コードは次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="c2f43-180">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="c2f43-181">コードから、クリック可能な相互参照を含む、詳細なドキュメント Web サイトを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-181">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="c2f43-182">ただし、別の問題に直面します。コードが読みにくくなります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-182">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="c2f43-183">大量の情報を処理する必要があり、このコードを利用する開発者にとって非常に厄介です。</span><span class="sxs-lookup"><span data-stu-id="c2f43-183">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="c2f43-184">さいわい、これに対処するのに役立つ XML タグがあります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-184">Thankfully there's an XML tag that can help you deal with this:</span></span>

## \<include>

<span data-ttu-id="c2f43-185">`<include>` タグでは、文書化コメントをソース コード ファイルに直接配置するのではなく、ソース コードの型とメンバーを記述した別個の XML ファイル内のコメントを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-185">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="c2f43-186">ここで、すべての XML タグを、`docs.xml` という別の XML ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-186">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="c2f43-187">ファイルの名前は何でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="c2f43-187">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="c2f43-188">上に示した XML では、各メンバーの文書化コメントが、タグの働きを表す名前の付いたタグの内側に直接記述されています。</span><span class="sxs-lookup"><span data-stu-id="c2f43-188">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="c2f43-189">自分の方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-189">You can choose your own strategy.</span></span>
<span data-ttu-id="c2f43-190">XML コメントを別のファイルに移動したので、`<include>` タグを使用して、コードがどのように読みやすくなるか見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="c2f43-190">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="c2f43-191">このようになります。コードは読みやすい状態に戻り、しかも文書化の情報は失われていません。</span><span class="sxs-lookup"><span data-stu-id="c2f43-191">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="c2f43-192">`file` は、文書化の情報を含む XML ファイルの名前を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="c2f43-192">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="c2f43-193">`path` は、指定した `file` に含まれる `tag name` への [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) クエリを表す属性です。</span><span class="sxs-lookup"><span data-stu-id="c2f43-193">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="c2f43-194">`name` は、コメントの前に配置するタグの名前指定子を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="c2f43-194">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="c2f43-195">`id` 属性は、`name` の代わりに使用でき、コメントの前にあるタグの ID を表します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-195">The `id` attribute, which can be used in place of `name`, represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="c2f43-196">ユーザー定義タグ</span><span class="sxs-lookup"><span data-stu-id="c2f43-196">User-defined tags</span></span>

<span data-ttu-id="c2f43-197">上に示したすべてのタグは、C# コンパイラで認識されるタグを表します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-197">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="c2f43-198">ただし、ユーザー独自のタグも自由に定義できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-198">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="c2f43-199">Sandcastle などのツールを使用すると、[\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) や [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) などの追加のタグや、[名前空間の文書化](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-199">Tools like Sandcastle bring support for extra tags like [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) and [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="c2f43-200">カスタムまたは社内ドキュメント生成ツールを標準タグと共に使用して、HTML から PDF への複数の出力形式をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-200">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="c2f43-201">推奨事項</span><span class="sxs-lookup"><span data-stu-id="c2f43-201">Recommendations</span></span>

<span data-ttu-id="c2f43-202">コードを文書化することをお勧めするのには、さまざまな理由があります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-202">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="c2f43-203">いくつかのベスト プラクティス、一般的なユース ケースのシナリオ、XML 文書化タグを C# コードで使用するときに知っておく必要があることを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-203">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="c2f43-204">整合性を保つため、一般に公開されているすべての型とそのメンバーを文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-204">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="c2f43-205">必要な文書化はすべて実行してください。</span><span class="sxs-lookup"><span data-stu-id="c2f43-205">If you must do it, do it all.</span></span>
- <span data-ttu-id="c2f43-206">プライベート メンバーも XML コメントを使用して文書化できます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-206">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="c2f43-207">ただし、これによりライブラリの内部 (機密の可能性がある) の動作が公開されます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-207">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="c2f43-208">型とそのメンバーには、少なくとも `<summary>` タグが必要です。そのタグの内容が IntelliSense で必要なためです。</span><span class="sxs-lookup"><span data-stu-id="c2f43-208">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="c2f43-209">文書化のテキストは、句点で終わる完全な文を使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f43-209">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="c2f43-210">部分クラスは完全にサポートされ、文書化の情報は、その型の 1 つのエントリに連結されます。</span><span class="sxs-lookup"><span data-stu-id="c2f43-210">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="c2f43-211">コンパイラは、`<exception>`、`<include>`、`<param>`、`<see>`、`<seealso>`、`<typeparam>` の各タグの構文を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-211">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>`, and `<typeparam>` tags.</span></span>
- <span data-ttu-id="c2f43-212">コンパイラは、ファイルのパスおよびコードの他の部分への参照を含むパラメーターを検証します。</span><span class="sxs-lookup"><span data-stu-id="c2f43-212">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2f43-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2f43-213">See also</span></span>

- [<span data-ttu-id="c2f43-214">XML ドキュメント コメント (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c2f43-214">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="c2f43-215">ドキュメント コメント用の推奨タグ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c2f43-215">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
