---
title: 純粋関数型変換の概要
ms.date: 07/20/2015
ms.assetid: 82bf3348-c503-4854-a91f-71f9835779ff
ms.openlocfilehash: a76fa4031b8f5a00f14d4a8854a2d6c44972381f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338813"
---
# <a name="introduction-to-pure-functional-transformations-visual-basic"></a><span data-ttu-id="19b9e-102">Introduction to Pure Functional Transformations (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-102">Introduction to Pure Functional Transformations (Visual Basic)</span></span>
<span data-ttu-id="19b9e-103">ここでは、関数型変換の概要について、その基になる概念や、それをサポートする言語構成要素も含めて説明します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="19b9e-104">また、オブジェクト指向変換と関数型変換という 2 つのプログラミング方法を対比させて、関数型変換に移行するためのアドバイスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="19b9e-105">関数型変換はさまざまなプログラミング シナリオで使用できますが、ここでは XML 変換を具体例として取り上げます。</span><span class="sxs-lookup"><span data-stu-id="19b9e-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19b9e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="19b9e-106">In This Section</span></span>  
  
|<span data-ttu-id="19b9e-107">トピック</span><span class="sxs-lookup"><span data-stu-id="19b9e-107">Topic</span></span>|<span data-ttu-id="19b9e-108">説明</span><span class="sxs-lookup"><span data-stu-id="19b9e-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="19b9e-109">Concepts and Terminology (Functional Transformation) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-109">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="19b9e-110">純粋関数型変換の概念と用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="19b9e-111">Functional Programming vs. Imperative Programming (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-111">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="19b9e-112">関数型プログラミングを従来の命令型 (手続き型) プログラミングと比較対照します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="19b9e-113">Refactoring Into Pure Functions (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-113">Refactoring Into Pure Functions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="19b9e-114">純粋関数について説明し、純粋関数と純粋でない関数の例を示します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="19b9e-115">Applicability of Functional Transformation (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-115">Applicability of Functional Transformation (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="19b9e-116">関数型変換の一般的なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="19b9e-117">XML の関数型変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="19b9e-118">XML ツリーの変換のコンテキストにおける関数型変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="19b9e-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19b9e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="19b9e-119">See also</span></span>

- [<span data-ttu-id="19b9e-120">Pure Functional Transformations of XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19b9e-120">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
