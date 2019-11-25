---
title: 型変換
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: fbf0c9877cf9a9b4364c8c058c61e847ad7bf049
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348722"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="3cf36-102">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="3cf36-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="3cf36-103">The process of changing a value from one data type to another type is called *conversion*.</span><span class="sxs-lookup"><span data-stu-id="3cf36-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="3cf36-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span><span class="sxs-lookup"><span data-stu-id="3cf36-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="3cf36-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span><span class="sxs-lookup"><span data-stu-id="3cf36-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3cf36-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3cf36-106">In This Section</span></span>  
 [<span data-ttu-id="3cf36-107">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="3cf36-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="3cf36-108">Explains conversions classified by whether the destination type can hold the data.</span><span class="sxs-lookup"><span data-stu-id="3cf36-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="3cf36-109">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="3cf36-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="3cf36-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span><span class="sxs-lookup"><span data-stu-id="3cf36-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="3cf36-111">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="3cf36-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="3cf36-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span><span class="sxs-lookup"><span data-stu-id="3cf36-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="3cf36-113">How to: Convert an Object to Another Type in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cf36-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="3cf36-114">Shows how to convert an `Object` variable to any other data type.</span><span class="sxs-lookup"><span data-stu-id="3cf36-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="3cf36-115">配列変換</span><span class="sxs-lookup"><span data-stu-id="3cf36-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="3cf36-116">Steps you through the process of converting between arrays of different data types.</span><span class="sxs-lookup"><span data-stu-id="3cf36-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3cf36-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cf36-117">Related Sections</span></span>  
 [<span data-ttu-id="3cf36-118">データの種類</span><span class="sxs-lookup"><span data-stu-id="3cf36-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="3cf36-119">Introduces the Visual Basic data types and describes how to use them.</span><span class="sxs-lookup"><span data-stu-id="3cf36-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="3cf36-120">データの種類</span><span class="sxs-lookup"><span data-stu-id="3cf36-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="3cf36-121">Lists the elementary data types supplied by Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3cf36-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="3cf36-122">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="3cf36-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="3cf36-123">Discusses some common problems that can arise when working with data types.</span><span class="sxs-lookup"><span data-stu-id="3cf36-123">Discusses some common problems that can arise when working with data types.</span></span>
