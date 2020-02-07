---
title: ドキュメント コメント用の推奨タグ - C# プログラミング ガイド
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789724"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="498e5-102">ドキュメント コメント用の推奨タグ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="498e5-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="498e5-103">コード内のドキュメント コメントは、C# コンパイラによって処理され、 **/doc** コマンド ライン オプションで指定した名前のファイルに XML 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="498e5-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="498e5-104">コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="498e5-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="498e5-105">タグは、型や型メンバーなどのコード コンストラクターに対して処理されます。</span><span class="sxs-lookup"><span data-stu-id="498e5-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="498e5-106">ドキュメント コメントは、名前空間に適用できません。</span><span class="sxs-lookup"><span data-stu-id="498e5-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="498e5-107">コンパイラは、有効な XML のタグをすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="498e5-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="498e5-108">ユーザー ドキュメントで一般的に使用される機能を提供するタグを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="498e5-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="498e5-109">Tags</span><span class="sxs-lookup"><span data-stu-id="498e5-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="498e5-110">\<c></span><span class="sxs-lookup"><span data-stu-id="498e5-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="498e5-111">\<para></span><span class="sxs-lookup"><span data-stu-id="498e5-111">\<para></span></span>](./para.md)|<span data-ttu-id="498e5-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="498e5-113">\<value></span><span class="sxs-lookup"><span data-stu-id="498e5-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="498e5-114">\<code></span><span class="sxs-lookup"><span data-stu-id="498e5-114">\<code></span></span>](./code.md)|<span data-ttu-id="498e5-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="498e5-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="498e5-117">\<example></span><span class="sxs-lookup"><span data-stu-id="498e5-117">\<example></span></span>](./example.md)|[<span data-ttu-id="498e5-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="498e5-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="498e5-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="498e5-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="498e5-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="498e5-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="498e5-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="498e5-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="498e5-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="498e5-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="498e5-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="498e5-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="498e5-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="498e5-126">\<list></span><span class="sxs-lookup"><span data-stu-id="498e5-126">\<list></span></span>](./list.md)|[<span data-ttu-id="498e5-127">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="498e5-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="498e5-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="498e5-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="498e5-129">(\* は、コンパイラによって構文が検証されることを示します。)</span><span class="sxs-lookup"><span data-stu-id="498e5-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="498e5-130">ドキュメント コメントのテキストに山かっこを表示する場合は、`<` と `>` の HTML エンコードを使用します。これはそれぞれ、`&lt;` と `&gt;` になります。</span><span class="sxs-lookup"><span data-stu-id="498e5-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="498e5-131">このエンコードは次の例に示されています。</span><span class="sxs-lookup"><span data-stu-id="498e5-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="498e5-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="498e5-132">See also</span></span>

- [<span data-ttu-id="498e5-133">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="498e5-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="498e5-134">-doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="498e5-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="498e5-135">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="498e5-135">XML documentation comments</span></span>](./index.md)
