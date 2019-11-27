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
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351749"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="c2391-102">Visual Basic での XML へのアクセス</span><span class="sxs-lookup"><span data-stu-id="c2391-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="c2391-103">Visual Basic には、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 構造体にアクセスして移動するための XML 軸プロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c2391-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="c2391-104">これらのプロパティでは、XML 名を指定して要素と属性にアクセスできるように、特殊な構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2391-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="c2391-105">次の表に、Visual Basic の XML 要素と属性にアクセスできるようにする言語機能を示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="c2391-106">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2391-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="c2391-107">プロパティの説明</span><span class="sxs-lookup"><span data-stu-id="c2391-107">Property description</span></span>|<span data-ttu-id="c2391-108">例</span><span class="sxs-lookup"><span data-stu-id="c2391-108">Example</span></span>|<span data-ttu-id="c2391-109">説明</span><span class="sxs-lookup"><span data-stu-id="c2391-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="c2391-110">*子軸*</span><span class="sxs-lookup"><span data-stu-id="c2391-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="c2391-111">`contact` 要素の子要素であるすべての `phone` 要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2391-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="c2391-112">*属性軸*</span><span class="sxs-lookup"><span data-stu-id="c2391-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="c2391-113">`phone` 要素のすべての `type` 属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2391-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="c2391-114">*子孫軸*</span><span class="sxs-lookup"><span data-stu-id="c2391-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="c2391-115">発生した階層の深さに関係なく、`contacts` 要素のすべての `name` 要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2391-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="c2391-116">*拡張機能のインデクサー*</span><span class="sxs-lookup"><span data-stu-id="c2391-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="c2391-117">シーケンスから最初の `name` 要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2391-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="c2391-118">*値*</span><span class="sxs-lookup"><span data-stu-id="c2391-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="c2391-119">シーケンス内の最初のオブジェクトの文字列表現を取得します。シーケンスが空の場合は `Nothing` します。</span><span class="sxs-lookup"><span data-stu-id="c2391-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="c2391-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c2391-120">In This Section</span></span>  
 [<span data-ttu-id="c2391-121">方法: XML 子孫要素にアクセスする</span><span class="sxs-lookup"><span data-stu-id="c2391-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="c2391-122">子孫軸プロパティを使用して、指定した名前を持ち、指定した XML 要素の下に含まれるすべての XML 要素にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="c2391-123">方法: XML 子要素にアクセスする</span><span class="sxs-lookup"><span data-stu-id="c2391-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="c2391-124">子軸プロパティを使用して、XML 要素内で指定された名前を持つすべての XML 子要素にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="c2391-125">方法: XML 属性にアクセスする</span><span class="sxs-lookup"><span data-stu-id="c2391-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="c2391-126">属性軸プロパティを使用して、XML 要素内で指定した名前を持つすべての XML 属性にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="c2391-127">方法 : XML 名前空間プレフィックスを宣言して使用する</span><span class="sxs-lookup"><span data-stu-id="c2391-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="c2391-128">XML 名前空間プレフィックスを宣言し、それを使用して XML 要素を作成およびアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c2391-129">関連セクション</span><span class="sxs-lookup"><span data-stu-id="c2391-129">Related Sections</span></span>  
 [<span data-ttu-id="c2391-130">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2391-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="c2391-131">さまざまな XML アクセスプロパティについて説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="c2391-132">Visual Basic における LINQ to XML の概要</span><span class="sxs-lookup"><span data-stu-id="c2391-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="c2391-133">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2391-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c2391-134">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="c2391-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="c2391-135">Visual Basic での XML リテラルの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2391-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c2391-136">Visual Basic での XML の操作</span><span class="sxs-lookup"><span data-stu-id="c2391-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="c2391-137">Visual Basic での XML の読み込みと変更に関するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c2391-138">XML</span><span class="sxs-lookup"><span data-stu-id="c2391-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="c2391-139">Visual Basic での [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] の使用方法を説明するセクションへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c2391-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
