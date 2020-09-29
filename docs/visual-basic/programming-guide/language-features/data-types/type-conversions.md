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
ms.openlocfilehash: ee8700ea757cee9c20e2598de029f54ae33a7114
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090158"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="65c05-102">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="65c05-102">Type Conversions in Visual Basic</span></span>

<span data-ttu-id="65c05-103">あるデータ型から別の型に値を変更するプロセスは、"*変換*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="65c05-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="65c05-104">変換は、関連する型のデータ容量に応じて、"*拡大*" または "*縮小*" のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="65c05-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="65c05-105">また、ソース コードの構文に応じて、"*暗黙的*" または "*明示的*" があります。</span><span class="sxs-lookup"><span data-stu-id="65c05-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65c05-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65c05-106">In This Section</span></span>  

 [<span data-ttu-id="65c05-107">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="65c05-107">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)  
 <span data-ttu-id="65c05-108">変換先の型がデータを保持できるかどうかによって分類される変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="65c05-109">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="65c05-109">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)  
 <span data-ttu-id="65c05-110">Visual Basic によって自動的に実行されるかどうかによって分類される変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="65c05-111">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="65c05-111">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="65c05-112">文字列と、数値、`Boolean`、または日付/時刻値の間での変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="65c05-113">方法: Visual Basic でオブジェクトを別の型に変換する</span><span class="sxs-lookup"><span data-stu-id="65c05-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="65c05-114">`Object` 変数を他の任意のデータ型に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="65c05-115">配列変換</span><span class="sxs-lookup"><span data-stu-id="65c05-115">Array Conversions</span></span>](array-conversions.md)  
 <span data-ttu-id="65c05-116">さまざまなデータ型の配列間での変換を行う手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="65c05-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="65c05-117">Related Sections</span></span>  

 [<span data-ttu-id="65c05-118">データの種類</span><span class="sxs-lookup"><span data-stu-id="65c05-118">Data Types</span></span>](index.md)  
 <span data-ttu-id="65c05-119">Visual Basic のデータ型の概要とそれらの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="65c05-120">データの種類</span><span class="sxs-lookup"><span data-stu-id="65c05-120">Data Types</span></span>](../../../language-reference/data-types/index.md)  
 <span data-ttu-id="65c05-121">Visual Basic によって提供される基本データ型の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="65c05-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="65c05-122">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="65c05-122">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)  
 <span data-ttu-id="65c05-123">データ型を使用しているときに発生する一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c05-123">Discusses some common problems that can arise when working with data types.</span></span>
