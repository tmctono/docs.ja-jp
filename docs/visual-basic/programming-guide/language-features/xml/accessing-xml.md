---
title: Visual Basic での XML へのアクセス
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756963"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="a99eb-102">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="a99eb-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="a99eb-103">Visual Basic では XML 軸のプロパティにアクセスすると、移動[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]構造体。</span><span class="sxs-lookup"><span data-stu-id="a99eb-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="a99eb-104">これらのプロパティは、要素と属性を XML の名前を指定することでアクセスするために特別な構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="a99eb-105">次の表では、Visual Basic の XML 要素と属性にアクセスするための言語機能を示します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="a99eb-106">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="a99eb-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="a99eb-107">プロパティの説明</span><span class="sxs-lookup"><span data-stu-id="a99eb-107">Property description</span></span>|<span data-ttu-id="a99eb-108">例</span><span class="sxs-lookup"><span data-stu-id="a99eb-108">Example</span></span>|<span data-ttu-id="a99eb-109">説明</span><span class="sxs-lookup"><span data-stu-id="a99eb-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="a99eb-110">*子軸*</span><span class="sxs-lookup"><span data-stu-id="a99eb-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="a99eb-111">すべて取得`phone`要素の子要素である、`contact`要素。</span><span class="sxs-lookup"><span data-stu-id="a99eb-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="a99eb-112">*attribute 軸*</span><span class="sxs-lookup"><span data-stu-id="a99eb-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="a99eb-113">すべて取得`type`の属性、`phone`要素。</span><span class="sxs-lookup"><span data-stu-id="a99eb-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="a99eb-114">*descendant 軸*</span><span class="sxs-lookup"><span data-stu-id="a99eb-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="a99eb-115">すべて取得`name`の要素、`contacts`が発生した階層の深さに関係なく、要素。</span><span class="sxs-lookup"><span data-stu-id="a99eb-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="a99eb-116">*拡張機能インデクサー*</span><span class="sxs-lookup"><span data-stu-id="a99eb-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="a99eb-117">最初に取得`name`シーケンスから要素。</span><span class="sxs-lookup"><span data-stu-id="a99eb-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="a99eb-118">*value*</span><span class="sxs-lookup"><span data-stu-id="a99eb-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="a99eb-119">シーケンスの最初のオブジェクトの文字列表現を取得または`Nothing`シーケンスが空の場合。</span><span class="sxs-lookup"><span data-stu-id="a99eb-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a99eb-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a99eb-120">In This Section</span></span>  
 [<span data-ttu-id="a99eb-121">方法: XML 子孫要素にアクセス</span><span class="sxs-lookup"><span data-stu-id="a99eb-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="a99eb-122">子孫軸プロパティを使用して、指定した名前を持ち、指定された XML 要素に含まれるすべての XML 要素にアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a99eb-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="a99eb-123">方法: XML 子要素にアクセス</span><span class="sxs-lookup"><span data-stu-id="a99eb-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="a99eb-124">軸のプロパティを XML 要素で指定した名前を持つすべての XML 子要素にアクセスする子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="a99eb-125">方法: XML 属性にアクセス</span><span class="sxs-lookup"><span data-stu-id="a99eb-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="a99eb-126">属性軸プロパティを使用して、指定した名前の XML 要素であるすべての XML 属性にアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a99eb-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="a99eb-127">方法: 宣言および XML Namespace プレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="a99eb-128">XML 名前空間プレフィックスを宣言し、それを使用して作成し、XML 要素にアクセスする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a99eb-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a99eb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a99eb-129">Related Sections</span></span>  
 [<span data-ttu-id="a99eb-130">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="a99eb-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="a99eb-131">さまざまな XML へのアクセスのプロパティを記述するセクションへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="a99eb-132">Visual Basic における LINQ to XML の概要</span><span class="sxs-lookup"><span data-stu-id="a99eb-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="a99eb-133">使用の概要を提供します。 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Visual Basic でします。</span><span class="sxs-lookup"><span data-stu-id="a99eb-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a99eb-134">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="a99eb-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="a99eb-135">Visual Basic での XML リテラルの使用の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a99eb-136">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="a99eb-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="a99eb-137">読み込みと Visual Basic における XML の変更についてのセクションへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="a99eb-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a99eb-138">XML</span><span class="sxs-lookup"><span data-stu-id="a99eb-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="a99eb-139">使用する方法を説明するセクションへのリンクを提供します。 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Visual Basic でします。</span><span class="sxs-lookup"><span data-stu-id="a99eb-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
