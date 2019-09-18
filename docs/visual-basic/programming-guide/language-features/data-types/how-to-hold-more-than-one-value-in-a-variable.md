---
title: '方法: 1つの変数に複数の値を保持する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 8d07a34a98303f9d220dba0a3c955120b421340e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054194"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="d7be6-102">方法: 1つの変数に複数の値を保持する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7be6-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="d7be6-103">*複合データ型*として宣言すると、変数に複数の値が保持されます。</span><span class="sxs-lookup"><span data-stu-id="d7be6-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="d7be6-104">[複合データ型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)には、構造体、配列、およびクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d7be6-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="d7be6-105">複合データ型の変数は、基本データ型とその他の複合型の組み合わせを保持できます。</span><span class="sxs-lookup"><span data-stu-id="d7be6-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="d7be6-106">構造体とクラスは、データだけでなくコードも保持できます。</span><span class="sxs-lookup"><span data-stu-id="d7be6-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="d7be6-107">変数に複数の値を格納するには</span><span class="sxs-lookup"><span data-stu-id="d7be6-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="d7be6-108">変数に使用する複合データ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="d7be6-109">複合データ型がまだ定義されていない場合は、変数で使用できるように定義します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="d7be6-110">Structure[ステートメント](../../../../visual-basic/language-reference/statements/structure-statement.md)を使用して構造体を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="d7be6-111">[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用して配列を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="d7be6-112">Class[ステートメント](../../../../visual-basic/language-reference/statements/class-statement.md)を使用してクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="d7be6-113">ステートメントを`Dim`使用して変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="d7be6-114">変数名`As`の後に句を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="d7be6-115">キーワードの`As`後に、適切な複合データ型の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7be6-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7be6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7be6-116">See also</span></span>

- [<span data-ttu-id="d7be6-117">データの種類</span><span class="sxs-lookup"><span data-stu-id="d7be6-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d7be6-118">型文字</span><span class="sxs-lookup"><span data-stu-id="d7be6-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="d7be6-119">複合データ型</span><span class="sxs-lookup"><span data-stu-id="d7be6-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="d7be6-120">構造体</span><span class="sxs-lookup"><span data-stu-id="d7be6-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d7be6-121">配列</span><span class="sxs-lookup"><span data-stu-id="d7be6-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="d7be6-122">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d7be6-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="d7be6-123">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="d7be6-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
