---
title: '方法 : 解析エラーをキャッチする'
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: 14c4f76c5f10616f9346084cda276e2862b2b41d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353340"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="c1454-102">方法: 解析エラーをキャッチする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1454-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="c1454-103">このトピックでは、形式が正しくないか無効な XML を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1454-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="c1454-104">は、<xref:System.Xml.XmlReader> を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="c1454-104">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="c1454-105">形式が正しくない XML や無効な XML が [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] に渡されると、基になる <xref:System.Xml.XmlReader> クラスから例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c1454-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="c1454-106">XML を解析するさまざまなメソッド (<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> など) はこの例外をキャッチしません。この例外は、アプリケーションでキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="c1454-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="c1454-107">XML リテラルを使用する場合は、解析エラーを検出できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c1454-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="c1454-108">Visual Basic コンパイラは、形式が正しくないか無効な XML をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="c1454-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1454-109">例</span><span class="sxs-lookup"><span data-stu-id="c1454-109">Example</span></span>  
 <span data-ttu-id="c1454-110">次のコードでは、無効な XML の解析を試行します。</span><span class="sxs-lookup"><span data-stu-id="c1454-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="c1454-111">このコードを実行すると、次の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c1454-111">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="c1454-112"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>、<xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>、<xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>、および <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> メソッドによってスローされる例外の詳細については、<xref:System.Xml.XmlReader> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1454-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1454-113">参照</span><span class="sxs-lookup"><span data-stu-id="c1454-113">See also</span></span>

- [<span data-ttu-id="c1454-114">XML の解析 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1454-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
