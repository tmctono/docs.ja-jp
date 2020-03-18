---
title: XML 宣言付きのシリアル化 (C#)
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 4533d69f2b0bee68b4adee6e18fe28dde18078ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "66483482"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="fe029-102">XML 宣言付きのシリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe029-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="fe029-103">このトピックでは、シリアル化を実行する際に XML 宣言を生成するかどうかを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe029-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="fe029-104">XML 宣言の生成</span><span class="sxs-lookup"><span data-stu-id="fe029-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="fe029-105"><xref:System.IO.File> メソッドまたは <xref:System.IO.TextWriter> メソッドを使用して <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> または <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> にシリアル化すると、XML 宣言が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fe029-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="fe029-106"><xref:System.Xml.XmlWriter> にシリアル化する場合は、<xref:System.Xml.XmlWriterSettings> オブジェクトで指定したライター設定により、XML 宣言が生成されるかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="fe029-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="fe029-107">`ToString` メソッドを使用して文字列にシリアル化する場合、生成される XML には XML 宣言は含まれません。</span><span class="sxs-lookup"><span data-stu-id="fe029-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="fe029-108">XML 宣言付きのシリアル化</span><span class="sxs-lookup"><span data-stu-id="fe029-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="fe029-109">次の例では、<xref:System.Xml.Linq.XElement> を作成し、ドキュメントをファイルに保存して、そのファイルをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="fe029-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="fe029-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fe029-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="fe029-111">XML 宣言なしでのシリアル化</span><span class="sxs-lookup"><span data-stu-id="fe029-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="fe029-112"><xref:System.Xml.Linq.XElement> を <xref:System.Xml.XmlWriter> に保存する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="fe029-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="fe029-113">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fe029-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe029-114">参照</span><span class="sxs-lookup"><span data-stu-id="fe029-114">See also</span></span>

- [<span data-ttu-id="fe029-115">XML ツリーのシリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe029-115">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
