---
title: XML の作成
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 0777b428d651c09d4bfb9789ab7b2ac8e74cc32e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410284"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="aa630-102">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="aa630-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="aa630-103">Visual Basic では、コードで *XML リテラル* を直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa630-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="aa630-104">XML リテラル構文は [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] オブジェクトを表し、XML 1.0 構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="aa630-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="aa630-105">これにより、コードが最終的な XML と同じ構造を持つため、XML 要素、ドキュメント、およびフラグメントをプログラムで簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="aa630-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa630-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aa630-106">In This Section</span></span>  
  
|<span data-ttu-id="aa630-107">用語</span><span class="sxs-lookup"><span data-stu-id="aa630-107">Term</span></span>|<span data-ttu-id="aa630-108">定義</span><span class="sxs-lookup"><span data-stu-id="aa630-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="aa630-109">XML リテラルの概要</span><span class="sxs-lookup"><span data-stu-id="aa630-109">XML Literals Overview</span></span>](xml-literals-overview.md)|<span data-ttu-id="aa630-110">XML リテラルの概要と、それらが [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] とどのように関連しているかを説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="aa630-111">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="aa630-111">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)|<span data-ttu-id="aa630-112">XML リテラルでの埋め込み式の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="aa630-113">方法: XML リテラルを作成する</span><span class="sxs-lookup"><span data-stu-id="aa630-113">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)|<span data-ttu-id="aa630-114">XML リテラルを使用して、コードで XML 要素を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="aa630-115">XML リテラルでの空白文字</span><span class="sxs-lookup"><span data-stu-id="aa630-115">White Space in XML Literals</span></span>](white-space-in-xml-literals.md)|<span data-ttu-id="aa630-116">Visual Basic で XML リテラルの空白を処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="aa630-117">XML リテラルと XML 1.0 仕様</span><span class="sxs-lookup"><span data-stu-id="aa630-117">XML Literals and the XML 1.0 Specification</span></span>](xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="aa630-118">Visual Basic の XML リテラル構文が XML 1.0 仕様とどのように関連しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="aa630-119">方法: XML リテラルに式を埋め込む</span><span class="sxs-lookup"><span data-stu-id="aa630-119">How to: Embed Expressions in XML Literals</span></span>](how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="aa630-120">XML リテラルで埋め込み式を使用して、実行時にコンテンツを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="aa630-121">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="aa630-121">Names of Declared XML Elements and Attributes</span></span>](names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="aa630-122">XML 要素と属性に名前を付ける場合のガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aa630-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa630-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa630-123">See also</span></span>

- [<span data-ttu-id="aa630-124">XML</span><span class="sxs-lookup"><span data-stu-id="aa630-124">XML</span></span>](index.md)
