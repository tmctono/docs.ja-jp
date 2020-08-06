---
title: 段落とそのスタイルの取得 (C#)
description: 段落を取得した後、各段落のスタイルを識別するクエリを記述する方法について説明します。
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 94d01a13485f70bc9d9cef55b5f390c3b30d7f14
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303401"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="f526b-103">段落とそのスタイルの取得 (C#)</span><span class="sxs-lookup"><span data-stu-id="f526b-103">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="f526b-104">この例では、WordprocessingML ドキュメントから段落ノードを取得するクエリを記述します。</span><span class="sxs-lookup"><span data-stu-id="f526b-104">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="f526b-105">それぞれの段落のスタイルも特定します。</span><span class="sxs-lookup"><span data-stu-id="f526b-105">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="f526b-106">このクエリの基になった前の例「[既定の段落スタイルの検索 (C#)](./finding-the-default-paragraph-style.md)」のクエリでは、スタイルの一覧から既定のスタイルを取得しています。</span><span class="sxs-lookup"><span data-stu-id="f526b-106">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="f526b-107">スタイルが明示的に設定されていない段落のスタイルをクエリで特定するには、この情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="f526b-107">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="f526b-108">段落のスタイルは、`w:pPr` 要素を通して設定されます。この要素が含まれていない段落は、既定のスタイルを使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="f526b-108">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="f526b-109">このトピックでは、クエリを構成するいくつかの要素の意味を説明し、完全な作業例の一部分であるクエリを紹介します。</span><span class="sxs-lookup"><span data-stu-id="f526b-109">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f526b-110">例</span><span class="sxs-lookup"><span data-stu-id="f526b-110">Example</span></span>  
 <span data-ttu-id="f526b-111">ドキュメント内のすべての段落とそのスタイルを取得するクエリのソースは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f526b-111">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="f526b-112">この式は、前の例「[既定の段落スタイルの検索 (C#)](./finding-the-default-paragraph-style.md)」のクエリのソースと似ています。</span><span class="sxs-lookup"><span data-stu-id="f526b-112">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="f526b-113">主な違いは、<xref:System.Xml.Linq.XContainer.Descendants%2A> 軸の代わりに <xref:System.Xml.Linq.XContainer.Elements%2A> 軸を使用している点です。</span><span class="sxs-lookup"><span data-stu-id="f526b-113">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="f526b-114">クエリで <xref:System.Xml.Linq.XContainer.Descendants%2A> 軸を使用しているのは、セクションが含まれているドキュメントの場合、段落が本文要素の直接の子とならず、階層内で 2 つ下のレベルに位置するためです。</span><span class="sxs-lookup"><span data-stu-id="f526b-114">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="f526b-115">コードで <xref:System.Xml.Linq.XContainer.Descendants%2A> 軸を使用すると、ドキュメントでセクションが使用されているかどうかにかかわらず機能するようになります。</span><span class="sxs-lookup"><span data-stu-id="f526b-115">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f526b-116">例</span><span class="sxs-lookup"><span data-stu-id="f526b-116">Example</span></span>  
 <span data-ttu-id="f526b-117">クエリで `let` 句を使用して、スタイル ノードが含まれる要素を特定します。</span><span class="sxs-lookup"><span data-stu-id="f526b-117">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="f526b-118">要素がない場合は、`styleNode` が `null` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f526b-118">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="f526b-119">`let` 句は、まず <xref:System.Xml.Linq.XContainer.Elements%2A> 軸を使用して `pPr` という名前の要素すべてを検索し、次に <xref:System.Xml.Linq.Extensions.Elements%2A> 拡張メソッドを使用して `pStyle` という名前の子要素すべてを検索し、最後に <xref:System.Linq.Enumerable.FirstOrDefault%2A> 標準クエリ演算子を使用してコレクションをシングルトンに変換します。</span><span class="sxs-lookup"><span data-stu-id="f526b-119">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="f526b-120">コレクションが空の場合は、`styleNode` が `null` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f526b-120">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="f526b-121">これは、`pStyle` 子孫ノードを検索するのに便利な表現形式です。</span><span class="sxs-lookup"><span data-stu-id="f526b-121">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="f526b-122">`pPr` 子ノードが存在しない場合、コードが例外をスローして失敗することはなく、`styleNode` が `null` に設定されます。これは、この `let` 句で予期された動作です。</span><span class="sxs-lookup"><span data-stu-id="f526b-122">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="f526b-123">このクエリは、匿名型のコレクションを射影します。このコレクションには、`StyleName` および `ParagraphNode` の 2 つのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="f526b-123">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f526b-124">例</span><span class="sxs-lookup"><span data-stu-id="f526b-124">Example</span></span>  
 <span data-ttu-id="f526b-125">この例では、WordprocessingML ドキュメントを処理して、WordprocessingML ドキュメントから段落ノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="f526b-125">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="f526b-126">それぞれの段落のスタイルも特定します。</span><span class="sxs-lookup"><span data-stu-id="f526b-126">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="f526b-127">この例は、このチュートリアルのこれまでの例に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f526b-127">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="f526b-128">新しいクエリについては、以下のコード内にあるコメントで説明が示されています。</span><span class="sxs-lookup"><span data-stu-id="f526b-128">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="f526b-129">この例のソース ドキュメントを作成する手順については、「[ソースとなる Office Open XML ドキュメントの作成 (C#)](./creating-the-source-office-open-xml-document.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f526b-129">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="f526b-130">この例では、WindowsBase アセンブリに含まれるクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f526b-130">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="f526b-131">また、<xref:System.IO.Packaging?displayProperty=nameWithType> 名前空間内の型を使用します。</span><span class="sxs-lookup"><span data-stu-id="f526b-131">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="f526b-132">この例を「[ソースとなる Office Open XML ドキュメントの作成 (C#)](./creating-the-source-office-open-xml-document.md)」で説明されているドキュメントに適用すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f526b-132">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="f526b-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="f526b-133">Next Steps</span></span>  
 <span data-ttu-id="f526b-134">次のトピック (「[段落のテキストの取得 (C#)](./retrieving-the-text-of-the-paragraphs.md)」) では、段落のテキストを取得するクエリを記述します。</span><span class="sxs-lookup"><span data-stu-id="f526b-134">In the next topic, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f526b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f526b-135">See also</span></span>

- [<span data-ttu-id="f526b-136">チュートリアル: WordprocessingML ドキュメント内のコンテンツの操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="f526b-136">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
