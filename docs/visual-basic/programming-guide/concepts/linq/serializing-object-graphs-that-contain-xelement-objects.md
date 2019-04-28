---
title: XElement オブジェクト (Visual Basic) を含むオブジェクト グラフをシリアル化します。
ms.date: 07/20/2015
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
ms.openlocfilehash: ffb348a0305b0f94c0870edead2a4852eee237cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786568"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="fc1ee-102">XElement オブジェクト (Visual Basic) を含むオブジェクト グラフをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="fc1ee-103">このトピックでは、<xref:System.Xml.Linq.XElement> 型のオブジェクトへの参照が含まれているオブジェクト グラフのシリアル化機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="fc1ee-104">この種のシリアル化を円滑に行うために、<xref:System.Xml.Linq.XElement> は <xref:System.Xml.Serialization.IXmlSerializable> インターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="fc1ee-105">シリアル化を実装しているのは <xref:System.Xml.Linq.XElement> クラスだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc1ee-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fc1ee-106">In This Section</span></span>  
  
|<span data-ttu-id="fc1ee-107">トピック</span><span class="sxs-lookup"><span data-stu-id="fc1ee-107">Topic</span></span>|<span data-ttu-id="fc1ee-108">説明</span><span class="sxs-lookup"><span data-stu-id="fc1ee-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fc1ee-109">方法: XmlSerializer を使用してシリアル化する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc1ee-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="fc1ee-110"><xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="fc1ee-111">方法: DataContractSerializer の使用 (Visual Basic) をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="fc1ee-112"><xref:System.Runtime.Serialization.DataContractSerializer> を使用してシリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc1ee-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc1ee-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc1ee-113">See also</span></span>

- [<span data-ttu-id="fc1ee-114">高度な LINQ to XML プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc1ee-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
