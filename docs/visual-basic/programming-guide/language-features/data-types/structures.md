---
title: 構造体 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
ms.openlocfilehash: ebfc82665bb18d96c83db8f29a6c206a9a71fd7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663363"
---
# <a name="structures-visual-basic"></a><span data-ttu-id="d22d0-102">構造体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d22d0-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="d22d0-103">A*構造*汎化、ユーザー定義型 (UDT) の以前のバージョンの Visual Basic でサポートされているです。</span><span class="sxs-lookup"><span data-stu-id="d22d0-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of Visual Basic.</span></span> <span data-ttu-id="d22d0-104">フィールドに加えて、構造体は、プロパティ、メソッド、およびイベントを公開できます。</span><span class="sxs-lookup"><span data-stu-id="d22d0-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="d22d0-105">構造体が 1 つまたは複数のインターフェイスを実装して、フィールドごとに個別のアクセス レベルを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="d22d0-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="d22d0-106">構造を作成するさまざまな種類のデータ項目を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="d22d0-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="d22d0-107">構造体は、1 つまたは複数を関連付けます*要素*と構造体そのものです。</span><span class="sxs-lookup"><span data-stu-id="d22d0-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="d22d0-108">構造体を宣言するときに、*複合データ型*、し、その型の変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="d22d0-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="d22d0-109">構造体は、いくつかの関連情報を保持するために 1 つの変数が必要な場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d22d0-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="d22d0-110">たとえば、従業員の名前、電話の拡張機能、および給与をまとめておくためにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="d22d0-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="d22d0-111">詳細については、いくつかの変数を使用する可能性があります。 または構造体を定義し、1 人の従業員の変数を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d22d0-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="d22d0-112">多くの従業員とそのため、変数の多数のインスタンスがある場合、構造体の利点は明らかになります。</span><span class="sxs-lookup"><span data-stu-id="d22d0-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d22d0-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d22d0-113">In This Section</span></span>  
 [<span data-ttu-id="d22d0-114">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="d22d0-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="d22d0-115">構造体とその要素を宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d22d0-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="d22d0-116">構造体変数</span><span class="sxs-lookup"><span data-stu-id="d22d0-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="d22d0-117">構造体の変数に代入し、その要素へのアクセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d22d0-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="d22d0-118">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="d22d0-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="d22d0-119">構造体が配列、オブジェクト、プロシージャ、およびその他とどのようにやり取りする方法をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d22d0-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="d22d0-120">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="d22d0-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="d22d0-121">構造体とクラス間の相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="d22d0-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d22d0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d22d0-122">Related Sections</span></span>  
 [<span data-ttu-id="d22d0-123">データの種類</span><span class="sxs-lookup"><span data-stu-id="d22d0-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="d22d0-124">Visual Basic のデータ型を紹介し、それらを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d22d0-124">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="d22d0-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="d22d0-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="d22d0-126">Visual Basic によって提供される基本データ型を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d22d0-126">Lists the elementary data types supplied by Visual Basic.</span></span>
