---
title: インデックスによる順序付けられたノードの取得
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e4847dd6bc05127799cb6d8424a8fdb63fbc0f7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64590059"
---
# <a name="ordered-node-retrieval-by-index"></a><span data-ttu-id="36716-102">インデックスによる順序付けられたノードの取得</span><span class="sxs-lookup"><span data-stu-id="36716-102">Ordered Node Retrieval by Index</span></span>
<span data-ttu-id="36716-103">W3C (World Wide Web Consortium) の XML ドキュメント オブジェクト モデル (DOM) では、**XmlNamedNodeMap** によって処理される順序付けられていないノード セットとは対照的に、順序付けられたノードのリストを処理する機能を持った NodeList も定義しています。</span><span class="sxs-lookup"><span data-stu-id="36716-103">The World Wide Web Consortium (W3C) XML Document Object Model (DOM) also describes a NodeList, which has the ability to handle an ordered list of nodes, as opposed to the unordered set handled by the **XmlNamedNodeMap**.</span></span> <span data-ttu-id="36716-104">Microsoft .NET Framework の NodeList は **XmlNodeList** と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="36716-104">The NodeList in the Microsoft .NET Framework is called **XmlNodeList**.</span></span> <span data-ttu-id="36716-105">**XmlNodeList** を返すメソッドとプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="36716-105">Methods and properties that return an **XmlNodeList** are:</span></span>  
  
- <span data-ttu-id="36716-106">XmlNode.ChildNodes</span><span class="sxs-lookup"><span data-stu-id="36716-106">XmlNode.ChildNodes</span></span>  
  
- <span data-ttu-id="36716-107">XmlDocument.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="36716-107">XmlDocument.GetElementsByTagName</span></span>  
  
- <span data-ttu-id="36716-108">XmlElement.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="36716-108">XmlElement.GetElementsByTagName</span></span>  
  
- <span data-ttu-id="36716-109">XmlNode.SelectNodes</span><span class="sxs-lookup"><span data-stu-id="36716-109">XmlNode.SelectNodes</span></span>  
  
 <span data-ttu-id="36716-110">**XmlNodeList** には **Count** プロパティがあり、次のコード サンプルに示すように、ループを記述して **XmlNodeList** のノードを反復処理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="36716-110">The **XmlNodeList** has a **Count** property that can be used to write loops to iterate over the nodes in the **XmlNodeList**, as shown in the following code sample:</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{     
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}   
```  
  
 <span data-ttu-id="36716-111">**Count** プロパティの他に、**XmlNodeList** 内のノード コレクションに対して `foreach` スタイルの反復処理を実行する **GetEnumerator** メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="36716-111">In addition to the **Count** property, there is a **GetEnumerator** method that provides a, `foreach` style iteration over the collection of nodes in the **XmlNodeList**.</span></span> <span data-ttu-id="36716-112">`foreach` ステートメントの使用方法を次のコード サンプルに示します。</span><span class="sxs-lookup"><span data-stu-id="36716-112">The following code example shows the use of the `foreach` statement.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum          
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();    
     // Loop over the XmlNodeList using the enumerator ienum          
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 <span data-ttu-id="36716-113">**XmlNodeList** で利用可能なメソッドとプロパティの詳細については、「<xref:System.Xml.XmlNodeList>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36716-113">For more information on the methods and properties available on the **XmlNodeList**, see <xref:System.Xml.XmlNodeList>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36716-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="36716-114">See also</span></span>

- [<span data-ttu-id="36716-115">XML ドキュメント オブジェクト モデル (DOM)</span><span class="sxs-lookup"><span data-stu-id="36716-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
