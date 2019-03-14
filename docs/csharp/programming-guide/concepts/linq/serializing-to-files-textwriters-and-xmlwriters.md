---
title: ファイル、TextWriter、および XmlWriter へのシリアル化1
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: bfbb0376823159c2026140c4382f321a563d92de
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680218"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="053ca-102">ファイル、TextWriter、および XmlWriter へのシリアル化</span><span class="sxs-lookup"><span data-stu-id="053ca-102">Serializing to Files, TextWriters, and XmlWriters</span></span>

<span data-ttu-id="053ca-103">XML ツリーは、<xref:System.IO.File>、<xref:System.IO.TextWriter>、または <xref:System.Xml.XmlWriter> にシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="053ca-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="053ca-104">
  <xref:System.Xml.Linq.XDocument> メソッドを使用すると、<xref:System.Xml.Linq.XElement> や `ToString\` など任意の XML コンポーネントを文字列にシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="053ca-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>

<span data-ttu-id="053ca-105">文字列にシリアル化するときに書式設定されないようにするには、<xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="053ca-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="053ca-106">ファイルにシリアル化するときの既定の動作では、結果の XML ドキュメントの書式設定 (インデント設定) が行われます。</span><span class="sxs-lookup"><span data-stu-id="053ca-106">The default behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="053ca-107">インデントを設定する場合、XML ツリー内の意味のない空白は保持されません。</span><span class="sxs-lookup"><span data-stu-id="053ca-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="053ca-108">書式を設定してシリアル化するには、<xref:System.Xml.Linq.SaveOptions> を引数として受け取らない次のメソッドのいずれかのオーバーロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="053ca-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="053ca-109">インデントを設定せず、XML ツリー内の意味のない空白を保持できるようにするには、<xref:System.Xml.Linq.SaveOptions> を引数として受け取る次のメソッドのいずれかのオーバーロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="053ca-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="053ca-110">例については、該当するリファレンス トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="053ca-110">For examples, see the appropriate reference topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="053ca-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="053ca-111">See also</span></span>

- [<span data-ttu-id="053ca-112">XML ツリーのシリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="053ca-112">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
