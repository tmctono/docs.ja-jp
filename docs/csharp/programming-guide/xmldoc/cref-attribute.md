---
title: cref 属性 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: b06d0c9d447124dec7d8cf3c0cbbfd0daca78fe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157014"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="dcdad-102">cref 属性 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="dcdad-102">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="dcdad-103">XML ドキュメント タグの `cref` 属性は "コード参照" を意味します。</span><span class="sxs-lookup"><span data-stu-id="dcdad-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="dcdad-104">タグの内部テキストが、型、メソッド、プロパティなど、コード要素であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdad-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="dcdad-105">[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) のようなドキュメント ツールでは `cref` 属性が使用されて、型やメンバーが文書化されるページのハイパーリンクが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="dcdad-105">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="dcdad-106">例</span><span class="sxs-lookup"><span data-stu-id="dcdad-106">Example</span></span>

<span data-ttu-id="dcdad-107">次の例は、`cref`[see>\< タグで使用される ](./see.md) 属性のものです。</span><span class="sxs-lookup"><span data-stu-id="dcdad-107">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="dcdad-108">コンパイルすると、このプログラムの XML 出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dcdad-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="dcdad-109">たとえば、`cref` メソッドの `GetZero` 属性がコンパイラにより `"M:TestNamespace.TestClass.GetZero"` に変換されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dcdad-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="dcdad-110">"M:" プレフィックスは "method" という意味であり、DocFX や Sandcastle のようなドキュメント ツールで認識される規約です。</span><span class="sxs-lookup"><span data-stu-id="dcdad-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="dcdad-111">プレフィックスの完全一覧については、「[XML ファイルの処理](./processing-the-xml-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdad-111">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="dcdad-112">参照</span><span class="sxs-lookup"><span data-stu-id="dcdad-112">See also</span></span>

- [<span data-ttu-id="dcdad-113">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="dcdad-113">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="dcdad-114">ドキュメント コメント用の推奨タグ</span><span class="sxs-lookup"><span data-stu-id="dcdad-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
