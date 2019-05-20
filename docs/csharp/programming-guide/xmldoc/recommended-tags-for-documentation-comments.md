---
title: ドキュメント コメント用の推奨タグ - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 963be5273389ebbdb3458d41b0658de0d94bb2cd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634796"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="2f495-102">ドキュメント コメント用の推奨タグ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="2f495-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="2f495-103">コード内のドキュメント コメントは、C# コンパイラによって処理され、**/doc** コマンド ライン オプションで指定した名前のファイルに XML 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="2f495-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="2f495-104">コンパイラによって生成されたファイルに基づいて最終的なドキュメントを作成するには、カスタム ツールを作成するか、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f495-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="2f495-105">タグは、型や型メンバーなどのコード コンストラクターに対して処理されます。</span><span class="sxs-lookup"><span data-stu-id="2f495-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f495-106">ドキュメント コメントは、名前空間に適用できません。</span><span class="sxs-lookup"><span data-stu-id="2f495-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="2f495-107">コンパイラは、有効な XML のタグをすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="2f495-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="2f495-108">ユーザー ドキュメントで一般的に使用される機能を提供するタグを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2f495-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="2f495-109">Tags</span><span class="sxs-lookup"><span data-stu-id="2f495-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="2f495-110">\<c></span><span class="sxs-lookup"><span data-stu-id="2f495-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="2f495-111">\<para></span><span class="sxs-lookup"><span data-stu-id="2f495-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="2f495-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span></span>|  
|[<span data-ttu-id="2f495-113">\<code></span><span class="sxs-lookup"><span data-stu-id="2f495-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="2f495-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span></span>|<span data-ttu-id="2f495-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span></span>|  
|[<span data-ttu-id="2f495-116">\<example></span><span class="sxs-lookup"><span data-stu-id="2f495-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="2f495-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="2f495-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="2f495-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="2f495-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="2f495-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span></span>|<span data-ttu-id="2f495-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span></span>|<span data-ttu-id="2f495-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span></span>|  
|<span data-ttu-id="2f495-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span><span class="sxs-lookup"><span data-stu-id="2f495-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span></span>|[<span data-ttu-id="2f495-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="2f495-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="2f495-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="2f495-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="2f495-125">\<list></span><span class="sxs-lookup"><span data-stu-id="2f495-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="2f495-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="2f495-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="2f495-127">\<value></span><span class="sxs-lookup"><span data-stu-id="2f495-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="2f495-128">(\* は、コンパイラが構文を検証することを示します。)</span><span class="sxs-lookup"><span data-stu-id="2f495-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="2f495-129">ドキュメント コメントのテキストに山かっこを表示する場合は、次の例に示すように `<` と `>` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f495-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```csharp  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f495-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f495-130">See also</span></span>

- [<span data-ttu-id="2f495-131">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2f495-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2f495-132">/doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="2f495-132">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="2f495-133">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="2f495-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/index.md)
