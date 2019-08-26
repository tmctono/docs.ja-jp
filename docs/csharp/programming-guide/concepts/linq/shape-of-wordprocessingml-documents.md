---
title: WordprocessingML ドキュメントの構造 (C#)
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 84d893267c37ecf99a457ebb683d0451e2b4b68f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591049"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="9f9c5-102">WordprocessingML ドキュメントの構造 (C#)</span><span class="sxs-lookup"><span data-stu-id="9f9c5-102">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="9f9c5-103">このトピックでは、WordprocessingML ドキュメントの XML 構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="9f9c5-104">Microsoft Office 形式</span><span class="sxs-lookup"><span data-stu-id="9f9c5-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="9f9c5-105">2007 Microsoft Office システムのネイティブ ファイル形式は Office Open XML (一般的な呼称は Open XML) です。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="9f9c5-106">Open XML は Ecma 標準の XML ベースの形式であり、現在は ISO-IEC 標準としての検討が進められている段階です。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="9f9c5-107">Open XML 内のワード プロセッシング ファイルのマークアップ言語は WordprocessingML と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="9f9c5-108">このチュートリアルの例では、WordprocessingML ソース ファイルを入力として使用します。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="9f9c5-109">Microsoft Office 2003 を使用しており、Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats をインストールしている場合は、Office Open XML 形式でドキュメントを保存できます。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="9f9c5-110">WordprocessingML ドキュメントの構造</span><span class="sxs-lookup"><span data-stu-id="9f9c5-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="9f9c5-111">最初に理解する必要があるのは WordprocessingML ドキュメントの構造です。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="9f9c5-112">WordprocessingML ドキュメントには、ドキュメントの段落を含む本文要素 (名前は `w:body`) が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="9f9c5-113">各段落には、1 つ以上のテキスト ラン (名前は `w:r`) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="9f9c5-114">各テキスト ランには、1 つ以上のテキスト片 (名前は `w:t`) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="9f9c5-115">非常に単純な WordprocessingML ドキュメントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-115">The following is a very simple WordprocessingML document:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 <span data-ttu-id="9f9c5-116">このドキュメントには、2 つの段落が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-116">This document contains two paragraphs.</span></span> <span data-ttu-id="9f9c5-117">各段落には 1 つのテキスト ランが含まれており、各テキスト ランには 1 つのテキスト片が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="9f9c5-118">WordprocessingML ドキュメントの内容を XML 形式で表示する最も簡単な方法は、Microsoft Word を使用して WordprocessingML ドキュメントを作成および保存し、次のプログラムを実行してコンソールに XML を出力することです。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="9f9c5-119">この例では、WindowsBase アセンブリに含まれるクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="9f9c5-120">また、<xref:System.IO.Packaging?displayProperty=nameWithType> 名前空間内の型を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f9c5-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="9f9c5-121">外部リソース</span><span class="sxs-lookup"><span data-stu-id="9f9c5-121">External Resources</span></span>  
 [<span data-ttu-id="9f9c5-122">Office (2007) Open XML ファイル形式の概要</span><span class="sxs-lookup"><span data-stu-id="9f9c5-122">Introducing the Office (2007) Open XML File Formats</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)  
 [<span data-ttu-id="9f9c5-123">WordprocessingML の概要</span><span class="sxs-lookup"><span data-stu-id="9f9c5-123">Overview of WordprocessingML</span></span>](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)  
 [<span data-ttu-id="9f9c5-124">WordProcessingML ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="9f9c5-124">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)  
 [<span data-ttu-id="9f9c5-125">WordprocessingML の概要</span><span class="sxs-lookup"><span data-stu-id="9f9c5-125">Introduction to WordprocessingML</span></span>](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)  
 [<span data-ttu-id="9f9c5-126">Office 2003:XML リファレンス スキーマのダウンロード ページ</span><span class="sxs-lookup"><span data-stu-id="9f9c5-126">Office 2003: XML Reference Schemas Download page</span></span>](https://www.microsoft.com/download/details.aspx?id=101)  
  
## <a name="see-also"></a><span data-ttu-id="9f9c5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f9c5-127">See also</span></span>

- [<span data-ttu-id="9f9c5-128">チュートリアル:WordprocessingML ドキュメント内のコンテンツの操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="9f9c5-128">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
