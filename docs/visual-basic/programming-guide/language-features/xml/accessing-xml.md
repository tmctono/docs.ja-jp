---
title: XML へのアクセス
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 282b7d91ec7cfe2f587c67bc9a982f0da22ad925
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410310"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="11f40-102">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="11f40-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="11f40-103">Visual Basic には、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 構造体にアクセスして移動するための XML 軸プロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="11f40-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="11f40-104">これらのプロパティでは、XML 名を指定して、要素と属性にアクセスできる特殊な構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="11f40-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="11f40-105">次の表に、Visual Basic で XML 要素と属性にアクセスできる言語機能を一覧表示しています。</span><span class="sxs-lookup"><span data-stu-id="11f40-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="11f40-106">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="11f40-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="11f40-107">プロパティの説明</span><span class="sxs-lookup"><span data-stu-id="11f40-107">Property description</span></span>|<span data-ttu-id="11f40-108">例</span><span class="sxs-lookup"><span data-stu-id="11f40-108">Example</span></span>|<span data-ttu-id="11f40-109">説明</span><span class="sxs-lookup"><span data-stu-id="11f40-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="11f40-110">*子軸*</span><span class="sxs-lookup"><span data-stu-id="11f40-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="11f40-111">`contact` 要素の子要素であるすべての `phone` 要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="11f40-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="11f40-112">*属性軸*</span><span class="sxs-lookup"><span data-stu-id="11f40-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="11f40-113">`phone` 要素のすべての `type` 属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="11f40-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="11f40-114">*子孫軸*</span><span class="sxs-lookup"><span data-stu-id="11f40-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="11f40-115">`contacts` 要素のすべての `name` 要素を、それらが存在する階層の深さに関係なく、取得します。</span><span class="sxs-lookup"><span data-stu-id="11f40-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="11f40-116">*拡張インデクサー*</span><span class="sxs-lookup"><span data-stu-id="11f40-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="11f40-117">シーケンスから最初の `name` 要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="11f40-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="11f40-118">*value*</span><span class="sxs-lookup"><span data-stu-id="11f40-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="11f40-119">シーケンス内の最初のオブジェクトの文字列表現、またはシーケンスが空の場合は `Nothing` を取得します。</span><span class="sxs-lookup"><span data-stu-id="11f40-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="11f40-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="11f40-120">In This Section</span></span>  
 [<span data-ttu-id="11f40-121">方法: XML 子孫要素にアクセスする</span><span class="sxs-lookup"><span data-stu-id="11f40-121">How to: Access XML Descendant Elements</span></span>](how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="11f40-122">子孫軸プロパティを使用して、指定した名前を持ち、指定した XML 要素の下に含まれているすべての XML 要素にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="11f40-123">方法: XML 子要素にアクセスする</span><span class="sxs-lookup"><span data-stu-id="11f40-123">How to: Access XML Child Elements</span></span>](how-to-access-xml-child-elements.md)  
 <span data-ttu-id="11f40-124">子軸プロパティを使用して、XML 要素内で指定した名前を持つすべての XML 子要素にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="11f40-125">方法: XML 属性にアクセスする</span><span class="sxs-lookup"><span data-stu-id="11f40-125">How to: Access XML Attributes</span></span>](how-to-access-xml-attributes.md)  
 <span data-ttu-id="11f40-126">属性軸プロパティを使用して、XML 要素内で指定した名前を持つすべての XML 属性にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="11f40-127">方法: XML 名前空間プレフィックスを宣言して使用する</span><span class="sxs-lookup"><span data-stu-id="11f40-127">How to: Declare and Use XML Namespace Prefixes</span></span>](how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="11f40-128">XML 名前空間プレフィックスを宣言し、それを使用して XML 要素を作成し、アクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11f40-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="11f40-129">Related Sections</span></span>  
 [<span data-ttu-id="11f40-130">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="11f40-130">XML Axis Properties</span></span>](../../../language-reference/xml-axis/index.md)  
 <span data-ttu-id="11f40-131">さまざまな XML アクセス プロパティについて説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="11f40-132">Visual Basic における LINQ to XML の概要</span><span class="sxs-lookup"><span data-stu-id="11f40-132">Overview of LINQ to XML in Visual Basic</span></span>](overview-of-linq-to-xml.md)  
 <span data-ttu-id="11f40-133">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="11f40-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="11f40-134">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="11f40-134">Creating XML in Visual Basic</span></span>](creating-xml.md)  
 <span data-ttu-id="11f40-135">Visual Basic での XML リテラルの使用の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="11f40-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="11f40-136">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="11f40-136">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)  
 <span data-ttu-id="11f40-137">Visual Basic での XML の読み込みと変更に関するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="11f40-138">XML</span><span class="sxs-lookup"><span data-stu-id="11f40-138">XML</span></span>](index.md)  
 <span data-ttu-id="11f40-139">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用方法を説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="11f40-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
