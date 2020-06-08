---
title: XML ツリーのシリアル化
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 640dc49134e869b60b4fa1fcd9a71fb1d61d39db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411819"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="a13ae-102">XML ツリーのシリアル化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a13ae-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="a13ae-103">XML ツリーのシリアル化とは、XML ツリーから XML を生成することです。</span><span class="sxs-lookup"><span data-stu-id="a13ae-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="a13ae-104">ファイル、<xref:System.IO.TextWriter> クラスの具象実装、または <xref:System.Xml.XmlWriter> クラスの具象実装へのシリアル化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a13ae-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="a13ae-105">シリアル化では、</span><span class="sxs-lookup"><span data-stu-id="a13ae-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="a13ae-106">シリアル化された XML をインデントするかどうかや、XML 宣言を書き込むかどうかなど、さまざまな側面を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a13ae-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a13ae-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a13ae-107">In This Section</span></span>  
  
|<span data-ttu-id="a13ae-108">トピック</span><span class="sxs-lookup"><span data-stu-id="a13ae-108">Topic</span></span>|<span data-ttu-id="a13ae-109">説明</span><span class="sxs-lookup"><span data-stu-id="a13ae-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a13ae-110">シリアル化時の空白の維持</span><span class="sxs-lookup"><span data-stu-id="a13ae-110">Preserving White Space While Serializing</span></span>](preserving-white-space-while-serializing.md)|<span data-ttu-id="a13ae-111">XML ツリーをシリアル化する際の空白の動作を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a13ae-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="a13ae-112">XML 宣言付きのシリアル化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a13ae-112">Serializing with an XML Declaration (Visual Basic)</span></span>](serializing-with-an-xml-declaration.md)|<span data-ttu-id="a13ae-113">XML 宣言を含む XML ツリーをシリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a13ae-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="a13ae-114">ファイル、TextWriter、および XmlWriter へのシリアル化</span><span class="sxs-lookup"><span data-stu-id="a13ae-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="a13ae-115">ドキュメントを <xref:System.IO.File>、<xref:System.IO.TextWriter>、または <xref:System.Xml.XmlWriter> にシリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a13ae-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="a13ae-116">XmlReader へのシリアル化 (XSLT の呼び出し) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a13ae-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="a13ae-117"><xref:System.Xml.XmlReader> を作成して、別のモジュールが XML ツリーの内容を読み取れるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a13ae-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a13ae-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a13ae-118">See also</span></span>

- [<span data-ttu-id="a13ae-119">プログラミング ガイド (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a13ae-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](programming-guide-linq-to-xml.md)
