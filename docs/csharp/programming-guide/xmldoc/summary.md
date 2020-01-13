---
title: <summary> - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 63c65e11a274779015cf99859b7fa67bb536529d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711689"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="78d92-102">\<summary> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="78d92-102">\<summary> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="78d92-103">構文</span><span class="sxs-lookup"><span data-stu-id="78d92-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="78d92-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78d92-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="78d92-105">オブジェクトの概要。</span><span class="sxs-lookup"><span data-stu-id="78d92-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78d92-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="78d92-106">Remarks</span></span>  
 <span data-ttu-id="78d92-107">\<summary> タグは、型または型のメンバーの説明に使用します。</span><span class="sxs-lookup"><span data-stu-id="78d92-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="78d92-108">型の説明に補足情報を追加するには、[\<remarks>](./remarks.md) タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="78d92-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="78d92-109">[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのドキュメント ツールでコード要素のドキュメント ページへの内部ハイパーリンクを作成できるようにするには、[cref 属性](./cref-attribute.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="78d92-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="78d92-110">\<summary> タグのテキストは、IntelliSense の型に関する唯一のソースで、オブジェクト ブラウザー ウィンドウにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="78d92-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="78d92-111">コンパイル時に [-doc](../../language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。</span><span class="sxs-lookup"><span data-stu-id="78d92-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="78d92-112">コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="78d92-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78d92-113">例</span><span class="sxs-lookup"><span data-stu-id="78d92-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
 <span data-ttu-id="78d92-114">前の例では、次の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="78d92-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="78d92-115">例</span><span class="sxs-lookup"><span data-stu-id="78d92-115">Example</span></span>  
 <span data-ttu-id="78d92-116">ジェネリック型への `cref` 参照を作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="78d92-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]  
  
 <span data-ttu-id="78d92-117">前の例では、次の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="78d92-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="78d92-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="78d92-118">See also</span></span>

- [<span data-ttu-id="78d92-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="78d92-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="78d92-120">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="78d92-120">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
