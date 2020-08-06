---
title: XML ドキュメント機能を使用する方法 - C# プログラミング ガイド
description: XML ドキュメント機能を使用する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 9ad2cfe62c70174eec9020ad4c8ce11608aca36d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380671"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="99e80-104">XML ドキュメント機能を使用する方法</span><span class="sxs-lookup"><span data-stu-id="99e80-104">How to use the XML documentation features</span></span>

<span data-ttu-id="99e80-105">次の例では、ドキュメント化された型の基本的な概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="99e80-105">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="99e80-106">例</span><span class="sxs-lookup"><span data-stu-id="99e80-106">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="99e80-107">この例では、次の内容を含む *.xml* ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="99e80-107">The example generates an *.xml* file with the following contents.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="99e80-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="99e80-108">Compiling the code</span></span>

<span data-ttu-id="99e80-109">この例をコンパイルするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="99e80-109">To compile the example, enter the following command:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="99e80-110">このコマンドによって作成される XML ファイル *XMLsample.xml* は、ブラウザーで、または `TYPE` コマンドを使って、表示できます。</span><span class="sxs-lookup"><span data-stu-id="99e80-110">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the `TYPE` command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="99e80-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="99e80-111">Robust programming</span></span>

<span data-ttu-id="99e80-112">XML ドキュメントは、`///` で始まります。</span><span class="sxs-lookup"><span data-stu-id="99e80-112">XML documentation starts with `///`.</span></span> <span data-ttu-id="99e80-113">新しいプロジェクトを作成すると、開始の `///` 行がいくつか自動的に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="99e80-113">When you create a new project, the wizards put some starter `///` lines in for you.</span></span> <span data-ttu-id="99e80-114">これらのコメントの処理にはいくつか制限があります。</span><span class="sxs-lookup"><span data-stu-id="99e80-114">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="99e80-115">ドキュメントは整形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e80-115">The documentation must be well-formed XML.</span></span> <span data-ttu-id="99e80-116">XML が整形式ではない場合は、警告が生成され、エラーが発生したことを示すコメントがドキュメント ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="99e80-116">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="99e80-117">開発者は、独自のタグ セットを自由に作成できます。</span><span class="sxs-lookup"><span data-stu-id="99e80-117">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="99e80-118">[推奨されるタグのセット](recommended-tags-for-documentation-comments.md)があります。</span><span class="sxs-lookup"><span data-stu-id="99e80-118">There is a [recommended set of tags](recommended-tags-for-documentation-comments.md).</span></span> <span data-ttu-id="99e80-119">推奨されるタグの一部には特別な意味があります。</span><span class="sxs-lookup"><span data-stu-id="99e80-119">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="99e80-120">`<param>` タグは、パラメーターの記述に使用します。</span><span class="sxs-lookup"><span data-stu-id="99e80-120">The `<param>` tag is used to describe parameters.</span></span> <span data-ttu-id="99e80-121">このタグがあると、コンパイラは、パラメーターが存在すること、およびすべてのパラメーターがドキュメントで記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99e80-121">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="99e80-122">検証が失敗する場合は、コンパイラが警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="99e80-122">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="99e80-123">`cref` 属性は任意のタグにアタッチされて、コード要素を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="99e80-123">The `cref` attribute can be attached to any tag to reference a code element.</span></span> <span data-ttu-id="99e80-124">コンパイラは、このコード要素が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="99e80-124">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="99e80-125">検証が失敗する場合は、コンパイラが警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="99e80-125">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="99e80-126">コンパイラは、`cref` 属性で記述されている型を探すとき、`using` ステートメントに従います。</span><span class="sxs-lookup"><span data-stu-id="99e80-126">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="99e80-127">`<summary>` タグは、型またはメンバーに関する追加情報を表示するために、Visual Studio 内の IntelliSense によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="99e80-127">The `<summary>` tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99e80-128">XML ファイルでは、型とメンバーに関する完全な情報は提供されません (たとえば、型の情報は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="99e80-128">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="99e80-129">型またはメンバーに関する完全な情報を取得するには、ドキュメント ファイルと併せて、実際の型またはメンバーでリフレクションを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e80-129">To get full information about a type or member, use the documentation file together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="99e80-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="99e80-130">See also</span></span>

- [<span data-ttu-id="99e80-131">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="99e80-131">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="99e80-132">-doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="99e80-132">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="99e80-133">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="99e80-133">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="99e80-134">DocFX ドキュメント プロセッサ</span><span class="sxs-lookup"><span data-stu-id="99e80-134">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="99e80-135">Sandcastle ドキュメント プロセッサ</span><span class="sxs-lookup"><span data-stu-id="99e80-135">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
