---
title: '方法: 文字列を解析する (C#)'
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 16310e37afec950c372c7b47637986bb0eb399b8
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956616"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="9305d-102">方法: 文字列を解析する (C#)</span><span class="sxs-lookup"><span data-stu-id="9305d-102">How to: Parse a String (C#)</span></span>

<span data-ttu-id="9305d-103">このトピックでは、C# で文字列を解析して XML ツリーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9305d-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>

## <a name="example"></a><span data-ttu-id="9305d-104">例</span><span class="sxs-lookup"><span data-stu-id="9305d-104">Example</span></span>

<span data-ttu-id="9305d-105">次の C# コードは、XML 文字列を解析する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9305d-105">The following C# code shows how to parse an XML string:</span></span>

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

<span data-ttu-id="9305d-106">ルート `Contacts` ノードには、2 つの `Contact` ノードがあります。</span><span class="sxs-lookup"><span data-stu-id="9305d-106">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="9305d-107">解析された XML 内の特定のデータにアクセスするには、[XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) メソッドを使用します。この例では、ルート `Contacts` ノードの子要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="9305d-107">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="9305d-108">次の例では、最初の `Contact` ノードをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="9305d-108">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a><span data-ttu-id="9305d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="9305d-109">See also</span></span>

- [<span data-ttu-id="9305d-110">方法: 特定の属性を持つ要素を検索する (C#)</span><span class="sxs-lookup"><span data-stu-id="9305d-110">How to: Find an Element with a Specific Attribute (C#)</span></span>](how-to-find-an-element-with-a-specific-attribute.md)
