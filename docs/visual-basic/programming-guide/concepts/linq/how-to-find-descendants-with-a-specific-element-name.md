---
title: '方法: 特定の要素名を持つ子孫を検索する (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: 5c4556ae7bf4c7560618781be51e066f659b0b4c
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72249676"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a><span data-ttu-id="29ce4-102">方法: 特定の要素名を持つ子孫を検索する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29ce4-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>
<span data-ttu-id="29ce4-103">特定の名前を持つ子孫をすべて検索しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="29ce4-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="29ce4-104">すべての子孫を反復処理するコードを記述することもできますが、<xref:System.Xml.Linq.XContainer.Descendants%2A> 軸を使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="29ce4-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29ce4-105">例</span><span class="sxs-lookup"><span data-stu-id="29ce4-105">Example</span></span>  
 <span data-ttu-id="29ce4-106">要素名に基づいて子孫を検索する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="29ce4-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```vb  
Dim root As XElement = _  
    <root>  
        <para>  
            <r>  
                <t>Some text </t>  
            </r>  
            <n>  
                <r>  
                    <t>that is broken up into </t>  
                </r>  
            </n>  
            <n>  
                <r>  
                    <t>multiple segments.</t>  
                </r>  
            </n>  
        </para>  
    </root>  
  
Dim textSegs As IEnumerable(Of String) = _  
    From seg In root...<t> _  
    Select seg.Value  
  
Dim str As String = textSegs.Aggregate( _  
    New StringBuilder, _  
    Function(sb, i) sb.Append(i), _  
    Function(sb) sb.ToString)  
  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="29ce4-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="29ce4-107">This code produces the following output:</span></span>  
  
```console  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="29ce4-108">例</span><span class="sxs-lookup"><span data-stu-id="29ce4-108">Example</span></span>  
 <span data-ttu-id="29ce4-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="29ce4-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="29ce4-110">詳細については、「[名前空間の概要」 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29ce4-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <root>  
                <para>  
                    <r>  
                        <t>Some text </t>  
                    </r>  
                    <n>  
                        <r>  
                            <t>that is broken up into </t>  
                        </r>  
                    </n>  
                    <n>  
                        <r>  
                            <t>multiple segments.</t>  
                        </r>  
                    </n>  
                </para>  
            </root>  
  
        Dim textSegs As IEnumerable(Of String) = _  
            From seg In root...<t> _  
            Select seg.Value  
  
        Dim str As String = textSegs.Aggregate( _  
            New StringBuilder, _  
            Function(sb, i) sb.Append(i), _  
            Function(sb) sb.ToString)  
  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="29ce4-111">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="29ce4-111">This code produces the following output:</span></span>  
  
```console  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="29ce4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="29ce4-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- [<span data-ttu-id="29ce4-113">基本的なクエリ (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29ce4-113">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
