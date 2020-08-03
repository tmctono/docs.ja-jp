---
title: LINQ to XML の例をビルドする方法 (C#)
description: C# のコンパイルに必要とされる適切な using ディレクティブを指定して、指定されたスニペットと LINQ to XML の例を実行します。
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: f54944dcb68e1fd7d00f37c9c5381f345efc820e
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103590"
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="c8581-103">LINQ to XML の例をビルドする方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="c8581-103">How to build LINQ to XML examples (C#)</span></span>
<span data-ttu-id="c8581-104">このドキュメントに含まれている各種のスニペットおよびコード例では、さまざまな名前空間のクラスと型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8581-104">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="c8581-105">C# のコードをコンパイルする場合は、適切な `using` ディレクティブを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8581-105">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8581-106">例</span><span class="sxs-lookup"><span data-stu-id="c8581-106">Example</span></span>  
 <span data-ttu-id="c8581-107">次のコードには、C# のコード例をビルドおよび実行するために必要な `using` ディレクティブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8581-107">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="c8581-108">すべての `using` ディレクティブがすべてのコード例で必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8581-108">Not all `using` directives are required for every example.</span></span>  
  
```csharp  
using System;  
using System.Diagnostics;  
using System.Collections;  
using System.Collections.Generic;  
using System.Collections.Specialized;  
using System.Text;  
using System.Linq;  
using System.Xml;  
using System.Xml.Linq;  
using System.Xml.Schema;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
using System.IO;  
using System.Threading;  
using System.Reflection;  
using System.IO.Packaging;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8581-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8581-109">See also</span></span>

- [<span data-ttu-id="c8581-110">LINQ to XML プログラミングの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="c8581-110">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
