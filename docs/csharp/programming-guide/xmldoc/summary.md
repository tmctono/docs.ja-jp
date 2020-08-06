---
title: <summary> - C# プログラミング ガイド
description: 型または型メンバーの説明に <summary> 使用される XML タグについて説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: f9243e598aaf0c12dd48b48045f461b4b307c18f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380606"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="f1af3-105">\<summary> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f1af3-105">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="f1af3-106">構文</span><span class="sxs-lookup"><span data-stu-id="f1af3-106">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="f1af3-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1af3-107">Parameters</span></span>

- `description`

  <span data-ttu-id="f1af3-108">オブジェクトの概要。</span><span class="sxs-lookup"><span data-stu-id="f1af3-108">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1af3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1af3-109">Remarks</span></span>

<span data-ttu-id="f1af3-110">`<summary>` タグは、型または型メンバーの説明に使用します。</span><span class="sxs-lookup"><span data-stu-id="f1af3-110">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="f1af3-111">型の説明に補足情報を追加するには、[\<remarks>](./remarks.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1af3-111">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="f1af3-112">[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのドキュメント ツールでコード要素のドキュメント ページへの内部ハイパーリンクを作成できるようにするには、[cref 属性](./cref-attribute.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1af3-112">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="f1af3-113">`<summary>` タグのテキストは、IntelliSense の型に関する情報の唯一のソースで、[オブジェクト ブラウザー] ウィンドウにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1af3-113">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="f1af3-114">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="f1af3-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="f1af3-115">コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1af3-115">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="f1af3-116">例</span><span class="sxs-lookup"><span data-stu-id="f1af3-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="f1af3-117">前の例では、次の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f1af3-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            </summary>
            <seealso cref="M:TestClass.Main"/>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="f1af3-118">例</span><span class="sxs-lookup"><span data-stu-id="f1af3-118">Example</span></span>

<span data-ttu-id="f1af3-119">ジェネリック型への `cref` 参照を作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f1af3-119">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="f1af3-120">前の例では、次の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f1af3-120">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="f1af3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1af3-121">See also</span></span>

- [<span data-ttu-id="f1af3-122">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f1af3-122">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="f1af3-123">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="f1af3-123">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
