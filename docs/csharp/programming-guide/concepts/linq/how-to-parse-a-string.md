---
title: 文字列を解析する方法 (C#)
description: C# で文字列を解析して XML ツリーを作成する方法について説明します。 解析された XML 内の特定のデータにアクセスする方法について説明します。
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: a4664e090b6a44c52c519e61b66ccdc5d59a71f1
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104819"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="57f84-104">文字列を解析する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="57f84-104">How to parse a string (C#)</span></span>

<span data-ttu-id="57f84-105">このトピックでは、C# で文字列を解析して XML ツリーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57f84-105">This topic shows how to parse a string to create an XML tree in C#.</span></span>

## <a name="example"></a><span data-ttu-id="57f84-106">例</span><span class="sxs-lookup"><span data-stu-id="57f84-106">Example</span></span>

<span data-ttu-id="57f84-107">次の C# コードは、XML 文字列を解析する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="57f84-107">The following C# code shows how to parse an XML string:</span></span>

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

<span data-ttu-id="57f84-108">ルート `Contacts` ノードには、2 つの `Contact` ノードがあります。</span><span class="sxs-lookup"><span data-stu-id="57f84-108">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="57f84-109">解析された XML 内の特定のデータにアクセスするには、[XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) メソッドを使用します。この例では、ルート `Contacts` ノードの子要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="57f84-109">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="57f84-110">次の例では、最初の `Contact` ノードをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="57f84-110">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a><span data-ttu-id="57f84-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="57f84-111">See also</span></span>

- [<span data-ttu-id="57f84-112">特定の属性を持つ要素を検索する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="57f84-112">How to find an element with a specific attribute (C#)</span></span>](how-to-find-an-element-with-a-specific-attribute.md)
