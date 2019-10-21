---
title: ドキュメント コメント用の推奨タグ - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: d17ff0b78d8ae40916447e8e12da7948a21e5717
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523370"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="41963-102">ドキュメント コメント用の推奨タグ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="41963-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="41963-103">コード内のドキュメント コメントは、C# コンパイラによって処理され、 **/doc** コマンド ライン オプションで指定した名前のファイルに XML 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="41963-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="41963-104">コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="41963-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="41963-105">タグは、型や型メンバーなどのコード コンストラクターに対して処理されます。</span><span class="sxs-lookup"><span data-stu-id="41963-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41963-106">ドキュメント コメントは、名前空間に適用できません。</span><span class="sxs-lookup"><span data-stu-id="41963-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="41963-107">コンパイラは、有効な XML のタグをすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="41963-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="41963-108">ユーザー ドキュメントで一般的に使用される機能を提供するタグを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="41963-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="41963-109">Tags</span><span class="sxs-lookup"><span data-stu-id="41963-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="41963-110">\<c></span><span class="sxs-lookup"><span data-stu-id="41963-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="41963-111">\<para></span><span class="sxs-lookup"><span data-stu-id="41963-111">\<para></span></span>](./para.md)|<span data-ttu-id="41963-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="41963-113">\<code></span><span class="sxs-lookup"><span data-stu-id="41963-113">\<code></span></span>](./code.md)|<span data-ttu-id="41963-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="41963-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="41963-116">\<example></span><span class="sxs-lookup"><span data-stu-id="41963-116">\<example></span></span>](./example.md)|[<span data-ttu-id="41963-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="41963-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="41963-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="41963-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="41963-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="41963-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="41963-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="41963-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="41963-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="41963-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="41963-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="41963-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="41963-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="41963-125">\<list></span><span class="sxs-lookup"><span data-stu-id="41963-125">\<list></span></span>](./list.md)|[<span data-ttu-id="41963-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="41963-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="41963-127">\<value></span><span class="sxs-lookup"><span data-stu-id="41963-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="41963-128">(\* は、コンパイラが構文を検証することを示します。)</span><span class="sxs-lookup"><span data-stu-id="41963-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="41963-129">ドキュメント コメントのテキストに山かっこを表示する場合は、`<` と `>` の HTML エンコードを使用します。これはそれぞれ、`&lt;` と `&gt;` になります。</span><span class="sxs-lookup"><span data-stu-id="41963-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="41963-130">次の例でこのエンコードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="41963-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="41963-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="41963-131">See also</span></span>

- [<span data-ttu-id="41963-132">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="41963-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="41963-133">-doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="41963-133">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="41963-134">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="41963-134">XML Documentation Comments</span></span>](./index.md)
