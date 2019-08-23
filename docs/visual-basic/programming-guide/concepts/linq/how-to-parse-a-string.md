---
title: '方法: 文字列を解析する (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: b97ce93c1018ec48649ab8b259d5f1a07109b9fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956383"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="d17cc-102">方法: 文字列を解析する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d17cc-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="d17cc-103">このトピックでは、でC#XML ツリーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d17cc-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d17cc-104">例</span><span class="sxs-lookup"><span data-stu-id="d17cc-104">Example</span></span>  
 <span data-ttu-id="d17cc-105">`XElement.Parse`メソッドを使用して Visual Basic 内の文字列を解析できます。</span><span class="sxs-lookup"><span data-stu-id="d17cc-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="d17cc-106">ただし、次のコードに示すように XML リテラルを使用する方が効率的です。これは、XML リテラルでは、文字列から XML を解析する場合のようなパフォーマンスの低下がないためです。</span><span class="sxs-lookup"><span data-stu-id="d17cc-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="d17cc-107">XML リテラルを使用すると、XML をコピーして Visual Basic プログラムに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d17cc-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d17cc-108">テキストの解析やテキスト ファイルからの XML ドキュメントの読み込みは、関数型構築より非効率です。</span><span class="sxs-lookup"><span data-stu-id="d17cc-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="d17cc-109">XML ツリーをコードから初期化すると、関数型構築で必要となるプロセッサ時間は、テキストの解析に比べて短くなります。</span><span class="sxs-lookup"><span data-stu-id="d17cc-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
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
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d17cc-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d17cc-110">See also</span></span>

- [<span data-ttu-id="d17cc-111">XML の解析 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d17cc-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
