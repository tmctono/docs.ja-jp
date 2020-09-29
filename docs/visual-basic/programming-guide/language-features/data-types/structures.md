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
ms.openlocfilehash: 04ccb5d39ea7c76a1e75dbeafd9230f2cb604d7c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090236"
---
# <a name="structures-visual-basic"></a><span data-ttu-id="aae14-102">構造体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aae14-102">Structures (Visual Basic)</span></span>

<span data-ttu-id="aae14-103">"*構造体*" は、以前のバージョンの Visual Basic でサポートされていたユーザー定義型 (UDT) を一般化したものです。</span><span class="sxs-lookup"><span data-stu-id="aae14-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of Visual Basic.</span></span> <span data-ttu-id="aae14-104">フィールドに加えて、構造体はプロパティ、メソッド、およびイベントを公開できます。</span><span class="sxs-lookup"><span data-stu-id="aae14-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="aae14-105">構造体は 1 つ以上のインターフェイスを実装できます。また、各フィールドに対して個別のアクセス レベルを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="aae14-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="aae14-106">さまざまな型のデータ項目を組み合わせて 1 つの構造体を作成できます。</span><span class="sxs-lookup"><span data-stu-id="aae14-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="aae14-107">構造体によって、1つまたは複数の "*要素*" が互いに関連付けられます。要素は構造体自体とも関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="aae14-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="aae14-108">構造体を宣言すると、それは "*複合データ型*" になり、その型の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="aae14-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="aae14-109">構造体は、複数の関連する情報を 1 つの変数に保持する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="aae14-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="aae14-110">たとえば、従業員の名前、内線電話番号、および給与をまとめて保持したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="aae14-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="aae14-111">この情報のために複数の変数を使用することもできますが、構造体を定義し、1 つの従業員変数として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="aae14-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="aae14-112">多くの従業員がいて、その変数のインスタンスも多くなる場合に、構造体の利点は明らかです。</span><span class="sxs-lookup"><span data-stu-id="aae14-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aae14-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aae14-113">In This Section</span></span>  

 [<span data-ttu-id="aae14-114">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="aae14-114">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)  
 <span data-ttu-id="aae14-115">構造体とその要素を宣言する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aae14-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="aae14-116">構造体変数</span><span class="sxs-lookup"><span data-stu-id="aae14-116">Structure Variables</span></span>](structure-variables.md)  
 <span data-ttu-id="aae14-117">構造体を変数に代入し、その要素にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aae14-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="aae14-118">構造体とその他のプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="aae14-118">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)  
 <span data-ttu-id="aae14-119">構造体が、配列、オブジェクト、プロシージャなどとどのように相互作用するかをまとめています。</span><span class="sxs-lookup"><span data-stu-id="aae14-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="aae14-120">構造体とクラス</span><span class="sxs-lookup"><span data-stu-id="aae14-120">Structures and Classes</span></span>](structures-and-classes.md)  
 <span data-ttu-id="aae14-121">構造体とクラスの類似点と相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="aae14-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aae14-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="aae14-122">Related Sections</span></span>  

 [<span data-ttu-id="aae14-123">データの種類</span><span class="sxs-lookup"><span data-stu-id="aae14-123">Data Types</span></span>](index.md)  
 <span data-ttu-id="aae14-124">Visual Basic のデータ型の概要とそれらの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aae14-124">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="aae14-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="aae14-125">Data Types</span></span>](../../../language-reference/data-types/index.md)  
 <span data-ttu-id="aae14-126">Visual Basic によって提供される基本データ型の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aae14-126">Lists the elementary data types supplied by Visual Basic.</span></span>
