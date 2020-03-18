---
title: 解析エラーをキャッチする方法 (C#)
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 1a05037892061dec85e7837472e8ec13e076724b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141486"
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="26a9e-102">解析エラーをキャッチする方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="26a9e-102">How to catch parsing errors (C#)</span></span>
<span data-ttu-id="26a9e-103">このトピックでは、形式が正しくないか無効な XML を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26a9e-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="26a9e-104">は、<xref:System.Xml.XmlReader> を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="26a9e-104">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="26a9e-105">形式が正しくない XML や無効な XML が [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] に渡されると、基になる <xref:System.Xml.XmlReader> クラスから例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="26a9e-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="26a9e-106">XML を解析するさまざまなメソッド (<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType> など) はこの例外をキャッチしません。この例外は、アプリケーションでキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="26a9e-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26a9e-107">例</span><span class="sxs-lookup"><span data-stu-id="26a9e-107">Example</span></span>  
 <span data-ttu-id="26a9e-108">次のコードでは、無効な XML の解析を試行します。</span><span class="sxs-lookup"><span data-stu-id="26a9e-108">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="26a9e-109">このコードを実行すると、次の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="26a9e-109">When you run this code, it throws the following exception:</span></span>  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="26a9e-110"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>、<xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>、<xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>、および <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> メソッドによってスローされる例外の詳細については、<xref:System.Xml.XmlReader> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26a9e-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  