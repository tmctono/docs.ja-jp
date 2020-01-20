---
title: XML コメントによるコードの文書化
description: XML ドキュメント コメントを含むコードを文書化し、コンパイル時に XML ドキュメント ファイルを生成する方法を説明します。
ms.date: 02/14/2017
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 6aa52030e20f61b26311347a57629658ebe0e609
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713938"
---
# <a name="document-your-code-with-xml-comments"></a><span data-ttu-id="3e4d5-103">XML コメントを含むコードの文書化</span><span class="sxs-lookup"><span data-stu-id="3e4d5-103">Document your code with XML comments</span></span>

<span data-ttu-id="3e4d5-104">XML 文書化コメントは、ユーザー定義型またはユーザー定義メンバーの定義の上に追加する特殊なコメントです。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="3e4d5-105">このコメントが特殊な理由は、コンパイル時にコンパイラで処理して、XML 文書化ファイルを生成できることです。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="3e4d5-106">コンパイラによって生成された XML ファイルは、.NET アセンブリと共に配布できます。これにより、Visual Studio や他の IDE で、IntelliSense を使用して型やメンバーに関する概要情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-106">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="3e4d5-107">さらに、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) のようなツールを使用して XML ファイルを実行し、API リファレンスの Web サイトを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="3e4d5-108">XML 文書化コメントは、その他すべてのコメントと同じように、コンパイラによって無視されます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="3e4d5-109">コンパイル時に XML ファイルを生成するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="3e4d5-110">.NET Core を使用してコマンド ラインからアプリケーションを開発している場合は、.csproj プロジェクト ファイルの `<PropertyGroup>` セクションに `GenerateDocumentationFile` 要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-110">If you are developing an application with .NET Core from the command line, you can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="3e4d5-111">また、[`DocumentationFile` 要素](/visualstudio/msbuild/common-msbuild-project-properties)を使用して、ドキュメント ファイルへのパスを直接指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-111">You can also specify the path to the documentation file directly using [`DocumentationFile` element](/visualstudio/msbuild/common-msbuild-project-properties).</span></span> <span data-ttu-id="3e4d5-112">次の例では、プロジェクト ディレクトリの中に、アセンブリと同じルート ファイル名で XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-112">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```
   
   <span data-ttu-id="3e4d5-113">これは、次の指定と同じです。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-113">This is equivalent to the following:</span></span>
   
   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- <span data-ttu-id="3e4d5-114">Visual Studio を使用してアプリケーションを開発する場合は、プロジェクトを右クリックして、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="3e4d5-115">プロパティ ダイアログ ボックスで、 **[ビルド]** タブをクリックし、 **[XML ドキュメント ファイル]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="3e4d5-116">コンパイラがファイルを書き込む場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="3e4d5-117">コマンド ラインから .NET Framework アプリケーションをコンパイルする場合は、コンパイル時に [-doc コンパイラ オプション](language-reference/compiler-options/doc-compiler-option.md)を追加してください。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-117">If you are compiling a .NET Framework application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="3e4d5-118">XML 文書化コメントには、3 つのスラッシュ (`///`) と、XML 形式のコメント本文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="3e4d5-119">例:</span><span class="sxs-lookup"><span data-stu-id="3e4d5-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="3e4d5-120">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="3e4d5-120">Walkthrough</span></span>

<span data-ttu-id="3e4d5-121">基本的な数式ライブラリを文書化して、新しい開発者が理解/参加しやすく、サードパーティの開発者が使用しやすいものにする方法を確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third-party developers to use.</span></span>

<span data-ttu-id="3e4d5-122">シンプルな数式ライブラリのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="3e4d5-123">この例のライブラリは、4 つの主要な算術演算である `add`、 `subtract`、`multiply`、`divide` を、`int` と `double` のデータ型でサポートします。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-123">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="3e4d5-124">このライブラリを使用するがそのソース コードにはアクセスできないサード パーティの開発者向けに、コードから API リファレンス ドキュメントを作成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-124">Now you want to be able to create an API reference document from your code for third-party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="3e4d5-125">前述のように、このために XML ドキュメント タグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="3e4d5-126">そこで、C# コンパイラがサポートする標準の XML タグを紹介します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## <a name="summary"></a><span data-ttu-id="3e4d5-127">\<summary></span><span class="sxs-lookup"><span data-stu-id="3e4d5-127">\<summary></span></span>

<span data-ttu-id="3e4d5-128">`<summary>` タグは、型またはメンバーに関する簡単な情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-128">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="3e4d5-129">この例では、タグの使い方を示すために、このタグを `Math` クラス定義と最初の `Add` メソッドに追加しています。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-129">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="3e4d5-130">コードのそれ以外の部分にも適用してかまいません。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-130">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="3e4d5-131">`<summary>` は非常に重要なタグです。IntelliSense や API のリファレンス ドキュメントでは、このタグの内容が型やメンバーに関する主要な情報源であるため、このタグを記述に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-131">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e4d5-132">\<remarks></span><span class="sxs-lookup"><span data-stu-id="3e4d5-132">\<remarks></span></span>

<span data-ttu-id="3e4d5-133">`<remarks>` タグは、`<summary>` タグで提供される型やメンバーに関する情報を補足します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-133">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="3e4d5-134">この例では、このタグをクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-134">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a><span data-ttu-id="3e4d5-135">\<returns></span><span class="sxs-lookup"><span data-stu-id="3e4d5-135">\<returns></span></span>

<span data-ttu-id="3e4d5-136">`<returns>` タグは、メソッド宣言の戻り値を記述します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-136">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="3e4d5-137">前と同様に、次の例は最初の `Add` メソッドに追加した `<returns>` タグを示しています。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-137">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="3e4d5-138">その他のメソッドにも同様に追加できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-138">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a><span data-ttu-id="3e4d5-139">\<value></span><span class="sxs-lookup"><span data-stu-id="3e4d5-139">\<value></span></span>

<span data-ttu-id="3e4d5-140">`<value>` タグは、プロパティに対して使用する点を除いて、`<returns>` タグと同じです。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-140">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="3e4d5-141">`Math` ライブラリに `PI` という静的プロパティがある場合、このタグを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-141">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a><span data-ttu-id="3e4d5-142">\<example></span><span class="sxs-lookup"><span data-stu-id="3e4d5-142">\<example></span></span>

<span data-ttu-id="3e4d5-143">`<example>` タグを使用して XML 文書化情報に例を挿入します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-143">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="3e4d5-144">そのために、子 `<code>` タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-144">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="3e4d5-145">`code` タグは、長い例で改行とインデント設定を維持します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-145">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## <a name="para"></a><span data-ttu-id="3e4d5-146">\<para></span><span class="sxs-lookup"><span data-stu-id="3e4d5-146">\<para></span></span>

<span data-ttu-id="3e4d5-147">`<para>` タグは、親タグ内の内容を書式設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-147">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="3e4d5-148">通常、`<para>` は `<remarks>` や `<returns>` などのタグの内側で使用して、テキストを段落に分割します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-148">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="3e4d5-149">クラス定義で `<remarks>` タグの内容を書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-149">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a><span data-ttu-id="3e4d5-150">\<c></span><span class="sxs-lookup"><span data-stu-id="3e4d5-150">\<c></span></span>

<span data-ttu-id="3e4d5-151">これも書式設定のタグです。`<c>` タグは、テキストの一部をコードとしてマークするために使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-151">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="3e4d5-152">`<code>` タグに似ていますが、インラインで記述する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-152">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="3e4d5-153">タグの内容の一部として簡単なコード例を示すときに便利です。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-153">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="3e4d5-154">`Math` クラスのドキュメントを更新してみましょう。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-154">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a><span data-ttu-id="3e4d5-155">\<exception></span><span class="sxs-lookup"><span data-stu-id="3e4d5-155">\<exception></span></span>

<span data-ttu-id="3e4d5-156">`<exception>` タグを使用すると、メソッドで特定の例外がスローされる可能性を開発者に知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-156">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="3e4d5-157">`Math` ライブラリを見てみると、特定の条件が満たされた場合、両方の `Add` メソッドで例外がスローされることがわかります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-157">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="3e4d5-158">一方、少しわかりにくいですが、`b`パラメーターが 0 の場合は整数の `Divide` メソッドでも例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-158">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="3e4d5-159">ここで、このメソッドに例外のドキュメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-159">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="3e4d5-160">`cref` 属性は、現在のコンパイル環境から使用できる例外の参照を表します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-160">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="3e4d5-161">プロジェクトまたは参照されたアセンブリに定義されている任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-161">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="3e4d5-162">コンパイラはその値を解決できない場合、警告を出します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-162">The compiler will issue a warning if its value cannot be resolved.</span></span>

## <a name="see"></a><span data-ttu-id="3e4d5-163">\<see></span><span class="sxs-lookup"><span data-stu-id="3e4d5-163">\<see></span></span>

<span data-ttu-id="3e4d5-164">`<see>` タグでは、別のコード要素のドキュメント ページへのクリック可能なリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-164">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="3e4d5-165">次の例では、2 つの `Add` メソッドの間にクリック可能なリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-165">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="3e4d5-166">`cref` は**必須**属性です。現在のコンパイル環境から使用できる型またはその型のメンバーへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-166">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="3e4d5-167">プロジェクトまたは参照されたアセンブリに定義されている任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-167">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="seealso"></a><span data-ttu-id="3e4d5-168">\<seealso></span><span class="sxs-lookup"><span data-stu-id="3e4d5-168">\<seealso></span></span>

<span data-ttu-id="3e4d5-169">`<seealso>` タグは、`<see>` タグと同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-169">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="3e4d5-170">唯一の違いは、このタグの内容が一般的に「関連項目」セクションに配置されることです。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-170">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="3e4d5-171">ここで、`seealso` タグを整数の `Add` メソッドに追加して、クラス内の、整数パラメーターを受け取る他のメソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-171">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="3e4d5-172">`cref` 属性は、現在のコンパイル環境から使用できる型またはその型のメンバーへの参照を表します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-172">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="3e4d5-173">プロジェクトまたは参照されたアセンブリに定義されている任意の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-173">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="param"></a><span data-ttu-id="3e4d5-174">\<param></span><span class="sxs-lookup"><span data-stu-id="3e4d5-174">\<param></span></span>

<span data-ttu-id="3e4d5-175">`<param>` タグは、メソッドのパラメーターを記述するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-175">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="3e4d5-176">double 型の `Add` メソッドでの例を示します。タグで記述するパラメーターは**必須** `name` 属性です。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-176">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a><span data-ttu-id="3e4d5-177">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="3e4d5-177">\<typeparam></span></span>

<span data-ttu-id="3e4d5-178">`<typeparam>` タグは、`<param>` タグと同じように使用しますが、ジェネリック型またはメソッド宣言で、ジェネリック パラメーターを記述するために使用する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-178">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="3e4d5-179">簡単なジェネリック メソッドを `Math` クラスに追加して、ある数量が別の数量より大きいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-179">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a><span data-ttu-id="3e4d5-180">\<paramref></span><span class="sxs-lookup"><span data-stu-id="3e4d5-180">\<paramref></span></span>

<span data-ttu-id="3e4d5-181">場合によって、`<summary>` タグでメソッドの動作を記述している最中に、パラメーターを参照することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-181">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="3e4d5-182">そのような場合は、`<paramref>` タグがまさに適しています。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-182">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="3e4d5-183">double 型に基づく `Add` メソッドの概要を更新しましょう。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-183">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="3e4d5-184">`<param>` タグと同様に、パラメーター名は**必須** `name` 属性で指定されます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-184">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a><span data-ttu-id="3e4d5-185">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="3e4d5-185">\<typeparamref></span></span>

<span data-ttu-id="3e4d5-186">`<typeparamref>` タグは、`<paramref>` タグと同じように使用しますが、ジェネリック型またはメソッド宣言で、ジェネリック パラメーターを記述するために使用する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-186">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="3e4d5-187">以前に作成した同じジェネリック メソッドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-187">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a><span data-ttu-id="3e4d5-188">\<list></span><span class="sxs-lookup"><span data-stu-id="3e4d5-188">\<list></span></span>

<span data-ttu-id="3e4d5-189">`<list>` タグは、文書化の情報を順序付きリスト、順不同のリスト、または表として書式設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-189">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="3e4d5-190">`Math` ライブラリがサポートするそれぞれの算術演算の順不同のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-190">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="3e4d5-191">`type` 属性を `number` または `table` に変更することで、順序付きリストまたは表をそれぞれ作成できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-191">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="put-it-all-together"></a><span data-ttu-id="3e4d5-192">まとめ</span><span class="sxs-lookup"><span data-stu-id="3e4d5-192">Put it all together</span></span>

<span data-ttu-id="3e4d5-193">ここまで、チュートリアルに沿ってコードに必要なタグを適用し、コードは次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-193">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="3e4d5-194">コードから、クリック可能な相互参照を含む、詳細なドキュメント Web サイトを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-194">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="3e4d5-195">ただし、別の問題に直面します。コードが読みにくくなります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-195">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="3e4d5-196">大量の情報を処理する必要があり、このコードを利用する開発者にとって非常に厄介です。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-196">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="3e4d5-197">さいわい、これに対処するのに役立つ XML タグがあります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-197">Thankfully there's an XML tag that can help you deal with this:</span></span>

## <a name="include"></a><span data-ttu-id="3e4d5-198">\<include></span><span class="sxs-lookup"><span data-stu-id="3e4d5-198">\<include></span></span>

<span data-ttu-id="3e4d5-199">`<include>` タグでは、文書化コメントをソース コード ファイルに直接配置するのではなく、ソース コードの型とメンバーを記述した別個の XML ファイル内のコメントを参照できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-199">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="3e4d5-200">ここで、すべての XML タグを、`docs.xml` という別の XML ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-200">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="3e4d5-201">ファイルの名前は何でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-201">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="3e4d5-202">上に示した XML では、各メンバーの文書化コメントが、タグの働きを表す名前の付いたタグの内側に直接記述されています。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-202">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="3e4d5-203">自分の方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-203">You can choose your own strategy.</span></span>
<span data-ttu-id="3e4d5-204">XML コメントを別のファイルに移動したので、`<include>` タグを使用して、コードがどのように読みやすくなるか見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-204">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="3e4d5-205">このようになります。コードは読みやすい状態に戻り、しかも文書化の情報は失われていません。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-205">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="3e4d5-206">`file` は、文書化の情報を含む XML ファイルの名前を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-206">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="3e4d5-207">`path` は、指定した `file` に含まれる `tag name` への [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) クエリを表す属性です。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-207">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="3e4d5-208">`name` は、コメントの前に配置するタグの名前指定子を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-208">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="3e4d5-209">`id` 属性は、`name` の代わりに使用でき、コメントの前にあるタグの ID を表します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-209">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="3e4d5-210">ユーザー定義タグ</span><span class="sxs-lookup"><span data-stu-id="3e4d5-210">User-defined tags</span></span>

<span data-ttu-id="3e4d5-211">上に示したすべてのタグは、C# コンパイラで認識されるタグを表します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-211">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="3e4d5-212">ただし、ユーザー独自のタグも自由に定義できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-212">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="3e4d5-213">Sandcastle などのツールを使用すると、[\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm)、[\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) などの追加のタグや、[名前空間の文書化](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-213">Tools like Sandcastle bring support for extra tags like [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) and [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="3e4d5-214">カスタムまたは社内ドキュメント生成ツールを標準タグと共に使用して、HTML から PDF への複数の出力形式をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-214">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="3e4d5-215">推奨事項</span><span class="sxs-lookup"><span data-stu-id="3e4d5-215">Recommendations</span></span>

<span data-ttu-id="3e4d5-216">コードを文書化することをお勧めするのには、さまざまな理由があります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-216">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="3e4d5-217">いくつかのベスト プラクティス、一般的なユース ケースのシナリオ、XML 文書化タグを C# コードで使用するときに知っておく必要があることを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-217">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="3e4d5-218">整合性を保つため、一般に公開されているすべての型とそのメンバーを文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-218">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="3e4d5-219">必要な文書化はすべて実行してください。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-219">If you must do it, do it all.</span></span>
- <span data-ttu-id="3e4d5-220">プライベート メンバーも XML コメントを使用して文書化できます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-220">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="3e4d5-221">ただし、これによりライブラリの内部 (機密の可能性がある) の動作が公開されます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-221">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="3e4d5-222">型とそのメンバーには、少なくとも `<summary>` タグが必要です。そのタグの内容が IntelliSense で必要なためです。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-222">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="3e4d5-223">文書化のテキストは、句点で終わる完全な文を使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-223">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="3e4d5-224">部分クラスは完全にサポートされ、文書化の情報は、その型の 1 つのエントリに連結されます。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-224">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="3e4d5-225">コンパイラは、`<exception>`、`<include>`、`<param>`、`<see>`、`<seealso>`、`<typeparam>` の各タグの構文を確認します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-225">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>`, and `<typeparam>` tags.</span></span>
- <span data-ttu-id="3e4d5-226">コンパイラは、ファイルのパスおよびコードの他の部分への参照を含むパラメーターを検証します。</span><span class="sxs-lookup"><span data-stu-id="3e4d5-226">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e4d5-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e4d5-227">See also</span></span>

- [<span data-ttu-id="3e4d5-228">XML ドキュメント コメント (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3e4d5-228">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="3e4d5-229">ドキュメント コメント用の推奨タグ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3e4d5-229">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
