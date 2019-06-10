---
title: XML ツリー内の要素、属性、およびノードの変更
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 93a4d67129e22d0bbeef464c1d4d8758439edb7b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484234"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="06a3f-102">XML ツリー内の要素、属性、およびノードの変更</span><span class="sxs-lookup"><span data-stu-id="06a3f-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="06a3f-103">次の表は、要素、その子要素、またはその属性の変更に使用できるメソッドとプロパティについてまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="06a3f-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="06a3f-104">次のメソッドは、<xref:System.Xml.Linq.XElement> を変更します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="06a3f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="06a3f-105">Method</span></span>|<span data-ttu-id="06a3f-106">説明</span><span class="sxs-lookup"><span data-stu-id="06a3f-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-107">要素を解析された XML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="06a3f-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-108">要素のすべてのコンテンツ (子ノードおよび属性) を削除します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-109">要素の属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-110">要素のすべてのコンテンツ (子ノードおよび属性) を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="06a3f-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-111">要素の属性を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="06a3f-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-112">属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-112">Sets the value of an attribute.</span></span> <span data-ttu-id="06a3f-113">属性が存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="06a3f-114">値に `null` が設定された場合は、属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-115">子要素の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-115">Sets the value of a child element.</span></span> <span data-ttu-id="06a3f-116">要素が存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="06a3f-117">値に `null` が設定された場合は、要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-118">要素のコンテンツ (子ノード) を、指定したテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="06a3f-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-119">要素の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="06a3f-120">次のメソッドは、<xref:System.Xml.Linq.XAttribute> を変更します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="06a3f-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="06a3f-121">Method</span></span>|<span data-ttu-id="06a3f-122">説明</span><span class="sxs-lookup"><span data-stu-id="06a3f-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-123">属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-124">属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="06a3f-125">次のメソッドは、<xref:System.Xml.Linq.XNode> (<xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XDocument> を含む) を変更します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="06a3f-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="06a3f-126">Method</span></span>|<span data-ttu-id="06a3f-127">説明</span><span class="sxs-lookup"><span data-stu-id="06a3f-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-128">ノードを新しいコンテンツに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="06a3f-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="06a3f-129">次のメソッドは、<xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XDocument>) を変更します。</span><span class="sxs-lookup"><span data-stu-id="06a3f-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="06a3f-130">メソッド</span><span class="sxs-lookup"><span data-stu-id="06a3f-130">Method</span></span>|<span data-ttu-id="06a3f-131">説明</span><span class="sxs-lookup"><span data-stu-id="06a3f-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="06a3f-132">子ノードを新しいコンテンツに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="06a3f-132">Replaces the children nodes with new content.</span></span>|  
