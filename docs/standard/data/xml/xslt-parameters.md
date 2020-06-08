---
title: XSLT パラメーター
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
ms.openlocfilehash: 7651360b375071c48ba0d23b64881ac794e51e86
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282533"
---
# <a name="xslt-parameters"></a><span data-ttu-id="967df-102">XSLT パラメーター</span><span class="sxs-lookup"><span data-stu-id="967df-102">XSLT Parameters</span></span>
<span data-ttu-id="967df-103">XSLT パラメーターを <xref:System.Xml.Xsl.XsltArgumentList> に追加するには、<xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="967df-103">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="967df-104">その時点で、修飾名と名前空間 URI がそのパラメーター オブジェクトに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="967df-104">A qualified name and namespace URI are associated with the parameter object at that time.</span></span>  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="967df-105">XSLT パラメーターを使用するために必要な処理</span><span class="sxs-lookup"><span data-stu-id="967df-105">To use an XSLT parameter</span></span>  
  
1. <span data-ttu-id="967df-106"><xref:System.Xml.Xsl.XsltArgumentList> オブジェクトを作成し、<xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> メソッドを使用してパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="967df-106">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the parameter using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span>  
  
2. <span data-ttu-id="967df-107">スタイル シートからパラメーターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="967df-107">Call the parameter from the style sheet.</span></span>  
  
3. <span data-ttu-id="967df-108"><xref:System.Xml.Xsl.XsltArgumentList> オブジェクトを <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="967df-108">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="parameter-types"></a><span data-ttu-id="967df-109">パラメーターの型</span><span class="sxs-lookup"><span data-stu-id="967df-109">Parameter Types</span></span>  
 <span data-ttu-id="967df-110">このパラメーター オブジェクトは、W3C 型に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="967df-110">The parameter object should correspond to a W3C type.</span></span> <span data-ttu-id="967df-111">対応する W3C 型、これと同等の Microsoft .NET のクラス (型)、および W3C 型が XPath 型か XSLT 型であるかを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="967df-111">The following table shows the corresponding W3C types, the equivalent Microsoft .NET classes (type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="967df-112">W3C 型</span><span class="sxs-lookup"><span data-stu-id="967df-112">W3C type</span></span>|<span data-ttu-id="967df-113">対応する .NET クラス (型)</span><span class="sxs-lookup"><span data-stu-id="967df-113">Equivalent .NET class (type)</span></span>|<span data-ttu-id="967df-114">XPath 型または XSLT 型</span><span class="sxs-lookup"><span data-stu-id="967df-114">XPath or XSLT type</span></span>|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="967df-115">XPath</span><span class="sxs-lookup"><span data-stu-id="967df-115">XPath</span></span>|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="967df-116">XPath</span><span class="sxs-lookup"><span data-stu-id="967df-116">XPath</span></span>|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="967df-117">XPath</span><span class="sxs-lookup"><span data-stu-id="967df-117">XPath</span></span>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="967df-118">XSLT</span><span class="sxs-lookup"><span data-stu-id="967df-118">XSLT</span></span>|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="967df-119">XPath</span><span class="sxs-lookup"><span data-stu-id="967df-119">XPath</span></span>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> <span data-ttu-id="967df-120">**XPathNavigator[]**</span><span class="sxs-lookup"><span data-stu-id="967df-120">**XPathNavigator[]**</span></span>|<span data-ttu-id="967df-121">XPath</span><span class="sxs-lookup"><span data-stu-id="967df-121">XPath</span></span>|  
  
 <span data-ttu-id="967df-122">\* これは単一のノードを含むノード セットに相当します。</span><span class="sxs-lookup"><span data-stu-id="967df-122">\*This is equivalent to a node set that contains a single node.</span></span>  
  
 <span data-ttu-id="967df-123">パラメーター オブジェクトが上記のクラスのいずれでもない場合、次の規則に従って型が変換されます。</span><span class="sxs-lookup"><span data-stu-id="967df-123">If the parameter object is not one of the above classes, it is converted according to the following rules.</span></span> <span data-ttu-id="967df-124">共通言語ランタイム (CLR) の数値型は、<xref:System.Double> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="967df-124">Common language runtime (CLR) numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="967df-125"><xref:System.DateTime> 型は <xref:System.String> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="967df-125">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="967df-126"><xref:System.Xml.XPath.IXPathNavigable> 型は <xref:System.Xml.XPath.XPathNavigator> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="967df-126"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="967df-127">**XPathNavigator[]** は <xref:System.Xml.XPath.XPathNodeIterator> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="967df-127">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="967df-128">その他の型はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="967df-128">All other types throw an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="967df-129">例</span><span class="sxs-lookup"><span data-stu-id="967df-129">Example</span></span>  
 <span data-ttu-id="967df-130">算出された割引日を保持するパラメーターを <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> メソッドを使用して作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="967df-130">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold calculated discount date.</span></span> <span data-ttu-id="967df-131">割引日は、発注日から 20 日後として算出されます。</span><span class="sxs-lookup"><span data-stu-id="967df-131">The discount date is calculated to be 20 days from the order date.</span></span>  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="967df-132">入力</span><span class="sxs-lookup"><span data-stu-id="967df-132">Input</span></span>  
  
##### <a name="orderxml"></a><span data-ttu-id="967df-133">order.xml</span><span class="sxs-lookup"><span data-stu-id="967df-133">order.xml</span></span>  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a><span data-ttu-id="967df-134">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="967df-134">discount.xsl</span></span>  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="967df-135">Output</span><span class="sxs-lookup"><span data-stu-id="967df-135">Output</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a><span data-ttu-id="967df-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="967df-136">See also</span></span>

- [<span data-ttu-id="967df-137">XSLT 変換</span><span class="sxs-lookup"><span data-stu-id="967df-137">XSLT Transformations</span></span>](xslt-transformations.md)
