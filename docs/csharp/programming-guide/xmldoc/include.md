---
title: <include> - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 26241dab70a3b6a0cf80b374868fa759647cd8d9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588002"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="c1a03-102">\<include> (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c1a03-102">\<include> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c1a03-103">構文</span><span class="sxs-lookup"><span data-stu-id="c1a03-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1a03-104">parameters</span><span class="sxs-lookup"><span data-stu-id="c1a03-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="c1a03-105">文書を含む XML ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c1a03-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="c1a03-106">ファイル名は、ソース コード ファイルの相対パスを使用して修飾することができます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-106">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="c1a03-107">`filename` を単一引用符 (' ') で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="c1a03-108">タグ `name` につながる `filename` 内のタグのパス。</span><span class="sxs-lookup"><span data-stu-id="c1a03-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="c1a03-109">パスを単一引用符 (' ') で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="c1a03-110">コメントの前に配置するタグの名前指定子。`name` には `id` が指定されます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="c1a03-111">コメントの前に配置するタグの ID。</span><span class="sxs-lookup"><span data-stu-id="c1a03-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="c1a03-112">ID は二重引用符 (" ") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1a03-113">解説</span><span class="sxs-lookup"><span data-stu-id="c1a03-113">Remarks</span></span>  
 <span data-ttu-id="c1a03-114">\<include> タグを使用して、ソース コード内の型とメンバーを記述する別のファイル内のコメントを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="c1a03-115">これは文書化のコメントをソース コード ファイル内に直接配置する方法の代替です。</span><span class="sxs-lookup"><span data-stu-id="c1a03-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="c1a03-116">別のファイルにドキュメントを配置することで、ソース コードから分離して、ソースの制御をドキュメントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="c1a03-117">1 人のユーザーがソース コード ファイルをチェックアウトし、他のユーザーがドキュメント ファイルをチェックアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="c1a03-118">\<include> タグは XML XPath 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1a03-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="c1a03-119">\<include> の使用をカスタマイズする方法については、XPath に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a03-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1a03-120">例</span><span class="sxs-lookup"><span data-stu-id="c1a03-120">Example</span></span>  
 <span data-ttu-id="c1a03-121">これは、複数ファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="c1a03-121">This is a multifile example.</span></span> <span data-ttu-id="c1a03-122">\<include> を使用する最初のファイルを以下に記載します。</span><span class="sxs-lookup"><span data-stu-id="c1a03-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 [!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]  
  
 <span data-ttu-id="c1a03-123">2 番目のファイル xml_include_tag.doc には、次のドキュメントのコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1a03-123">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a><span data-ttu-id="c1a03-124">プログラムの出力</span><span class="sxs-lookup"><span data-stu-id="c1a03-124">Program Output</span></span>  
 <span data-ttu-id="c1a03-125">Test および Test2 クラスをコンパイルするときにコマンド ライン `/doc:DocFileName.xml.` を使うと、以下の出力が生成されます。Visual Studio では、プロジェクト デザイナーの [ビルド] ウィンドウで、XML ドキュメント コメントのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1a03-125">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="c1a03-126">C# コンパイラが \<include> タグを認識すると、現在のソース ファイルではなく xml_include_tag.doc でドキュメントのコメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="c1a03-126">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="c1a03-127">コンパイラは次に、DocFileName.xml を生成します。これは、最終的なドキュメントを生成するために、[DocFX](https://dotnet.github.io/docfx/) や [Sandcastle](https://github.com/EWSoftware/SHFB) などのドキュメント ツールによって利用されます。</span><span class="sxs-lookup"><span data-stu-id="c1a03-127">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a><span data-ttu-id="c1a03-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1a03-128">See also</span></span>

- [<span data-ttu-id="c1a03-129">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c1a03-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c1a03-130">ドキュメント コメントとして推奨されるタグ</span><span class="sxs-lookup"><span data-stu-id="c1a03-130">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
