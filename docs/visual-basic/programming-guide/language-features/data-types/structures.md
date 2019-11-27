---
title: 構造体
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
ms.openlocfilehash: b5f1f8d6d783c6612fdb2bd2058b61a5a46024cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350774"
---
# <a name="structures-visual-basic"></a><span data-ttu-id="55c65-102">構造体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55c65-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="55c65-103">*構造体*は、以前のバージョンの Visual Basic でサポートされているユーザー定義型 (UDT) を一般化したものです。</span><span class="sxs-lookup"><span data-stu-id="55c65-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of Visual Basic.</span></span> <span data-ttu-id="55c65-104">フィールドに加えて、構造体は、プロパティ、メソッド、およびイベントを公開できます。</span><span class="sxs-lookup"><span data-stu-id="55c65-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="55c65-105">構造体は、1つまたは複数のインターフェイスを実装でき、各フィールドの個別のアクセスレベルを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="55c65-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="55c65-106">さまざまな種類のデータ項目を組み合わせて、構造体を作成できます。</span><span class="sxs-lookup"><span data-stu-id="55c65-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="55c65-107">構造体は、1つまたは複数の*要素*を互いに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="55c65-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="55c65-108">構造体を宣言すると、*複合データ型*になり、その型の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="55c65-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="55c65-109">構造体は、複数の関連する情報を1つの変数に保持する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="55c65-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="55c65-110">たとえば、従業員の名前、電話の内線番号、および給与をまとめて保持することができます。</span><span class="sxs-lookup"><span data-stu-id="55c65-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="55c65-111">この情報にはいくつかの変数を使用できます。また、構造を定義し、1つの employee 変数に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="55c65-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="55c65-112">多くの従業員がいて、その変数のインスタンスが多数ある場合、構造の利点が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="55c65-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55c65-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55c65-113">In This Section</span></span>  
 [<span data-ttu-id="55c65-114">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="55c65-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="55c65-115">構造体とその要素を宣言する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55c65-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="55c65-116">構造体変数</span><span class="sxs-lookup"><span data-stu-id="55c65-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="55c65-117">構造体を変数に割り当て、その要素にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55c65-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="55c65-118">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="55c65-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="55c65-119">構造体が配列、オブジェクト、プロシージャなどとどのように対話するかをまとめます。</span><span class="sxs-lookup"><span data-stu-id="55c65-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="55c65-120">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="55c65-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="55c65-121">構造体とクラスの類似点と相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="55c65-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55c65-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="55c65-122">Related Sections</span></span>  
 [<span data-ttu-id="55c65-123">データの種類</span><span class="sxs-lookup"><span data-stu-id="55c65-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="55c65-124">Visual Basic のデータ型について説明し、その使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55c65-124">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="55c65-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="55c65-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="55c65-126">Visual Basic によって提供される基本データ型の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="55c65-126">Lists the elementary data types supplied by Visual Basic.</span></span>
