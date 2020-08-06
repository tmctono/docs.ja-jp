---
title: XML ツリー内の要素、属性、およびノードの変更
description: 要素、その子ノード、またはその属性の変更に使用できるメソッドとプロパティについて説明します。
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: bfff882dc57a4f6f4b228563ac923122097d88d0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303167"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="356cb-103">XML ツリー内の要素、属性、およびノードの変更</span><span class="sxs-lookup"><span data-stu-id="356cb-103">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="356cb-104">次の表は、要素、その子要素、またはその属性の変更に使用できるメソッドとプロパティについてまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="356cb-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="356cb-105">次のメソッドは、<xref:System.Xml.Linq.XElement> を変更します。</span><span class="sxs-lookup"><span data-stu-id="356cb-105">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="356cb-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="356cb-106">Method</span></span>|<span data-ttu-id="356cb-107">説明</span><span class="sxs-lookup"><span data-stu-id="356cb-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-108">要素を解析された XML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="356cb-108">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-109">要素のすべてのコンテンツ (子ノードおよび属性) を削除します。</span><span class="sxs-lookup"><span data-stu-id="356cb-109">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-110">要素の属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="356cb-110">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-111">要素のすべてのコンテンツ (子ノードおよび属性) を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="356cb-111">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-112">要素の属性を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="356cb-112">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-113">属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="356cb-113">Sets the value of an attribute.</span></span> <span data-ttu-id="356cb-114">属性が存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="356cb-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="356cb-115">値に `null` が設定された場合は、属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="356cb-115">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-116">子要素の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="356cb-116">Sets the value of a child element.</span></span> <span data-ttu-id="356cb-117">要素が存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="356cb-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="356cb-118">値に `null` が設定された場合は、要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="356cb-118">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-119">要素のコンテンツ (子ノード) を、指定したテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="356cb-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-120">要素の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="356cb-120">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="356cb-121">次のメソッドは、<xref:System.Xml.Linq.XAttribute> を変更します。</span><span class="sxs-lookup"><span data-stu-id="356cb-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="356cb-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="356cb-122">Method</span></span>|<span data-ttu-id="356cb-123">説明</span><span class="sxs-lookup"><span data-stu-id="356cb-123">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-124">属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="356cb-124">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-125">属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="356cb-125">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="356cb-126">次のメソッドは、<xref:System.Xml.Linq.XNode> (<xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XDocument> を含む) を変更します。</span><span class="sxs-lookup"><span data-stu-id="356cb-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="356cb-127">メソッド</span><span class="sxs-lookup"><span data-stu-id="356cb-127">Method</span></span>|<span data-ttu-id="356cb-128">説明</span><span class="sxs-lookup"><span data-stu-id="356cb-128">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-129">ノードを新しいコンテンツに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="356cb-129">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="356cb-130">次のメソッドは、<xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XDocument>) を変更します。</span><span class="sxs-lookup"><span data-stu-id="356cb-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="356cb-131">メソッド</span><span class="sxs-lookup"><span data-stu-id="356cb-131">Method</span></span>|<span data-ttu-id="356cb-132">説明</span><span class="sxs-lookup"><span data-stu-id="356cb-132">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="356cb-133">子ノードを新しいコンテンツに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="356cb-133">Replaces the children nodes with new content.</span></span>|  
