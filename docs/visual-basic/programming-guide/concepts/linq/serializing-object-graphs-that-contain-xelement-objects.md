---
title: XElement オブジェクトを含むオブジェクト グラフのシリアル化
ms.date: 07/20/2015
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
ms.openlocfilehash: 5390cfaa77229b60af6388fc643544c539c15fe9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360684"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="08869-102">XElement オブジェクトを含むオブジェクト グラフのシリアル化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08869-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="08869-103">このトピックでは、<xref:System.Xml.Linq.XElement> 型のオブジェクトへの参照が含まれているオブジェクト グラフのシリアル化機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="08869-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="08869-104">この種のシリアル化を円滑に行うために、<xref:System.Xml.Linq.XElement> は <xref:System.Xml.Serialization.IXmlSerializable> インターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="08869-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="08869-105">シリアル化を実装しているのは <xref:System.Xml.Linq.XElement> クラスだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="08869-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08869-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="08869-106">In This Section</span></span>  
  
|<span data-ttu-id="08869-107">トピック</span><span class="sxs-lookup"><span data-stu-id="08869-107">Topic</span></span>|<span data-ttu-id="08869-108">説明</span><span class="sxs-lookup"><span data-stu-id="08869-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="08869-109">方法: XmlSerializer を使用してシリアル化する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08869-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="08869-110"><xref:System.Xml.Serialization.XmlSerializer> を使用してシリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08869-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="08869-111">方法: DataContractSerializer を使用してシリアル化する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08869-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="08869-112"><xref:System.Runtime.Serialization.DataContractSerializer> を使用してシリアル化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08869-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08869-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="08869-113">See also</span></span>

- [<span data-ttu-id="08869-114">高度な LINQ to XML プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08869-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
