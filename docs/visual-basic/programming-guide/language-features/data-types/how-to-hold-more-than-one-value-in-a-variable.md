---
title: '方法: 変数 (Visual Basic) では、複数の値を保持します。'
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
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332262"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="fbf27-102">方法: 変数 (Visual Basic) では、複数の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="fbf27-103">として宣言する場合、変数が 1 つ以上の値を保持する*複合データ型*します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="fbf27-104">[複合データ型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)構造体、配列、およびクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fbf27-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="fbf27-105">複合データ型の変数には、基本データ型とその他の複合型の組み合わせを保持できます。</span><span class="sxs-lookup"><span data-stu-id="fbf27-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="fbf27-106">構造体とクラスは、コードだけではなく、データを保持できます。</span><span class="sxs-lookup"><span data-stu-id="fbf27-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="fbf27-107">変数に 1 つ以上の値を保持するには</span><span class="sxs-lookup"><span data-stu-id="fbf27-107">To hold more than one value in a variable</span></span>  
  
1. <span data-ttu-id="fbf27-108">変数の使用する複合データ型を確認します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2. <span data-ttu-id="fbf27-109">複合データ型が既に定義されていない場合、変数が使用できるように定義します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="fbf27-110">含む構造体の定義、 [Structure ステートメント](../../../../visual-basic/language-reference/statements/structure-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="fbf27-111">配列を定義、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="fbf27-112">クラスを定義、[クラス ステートメント](../../../../visual-basic/language-reference/statements/class-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="fbf27-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3. <span data-ttu-id="fbf27-113">使用して変数を宣言、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="fbf27-113">Declare your variable with a `Dim` statement.</span></span>  
  
4. <span data-ttu-id="fbf27-114">変数名に続けて、`As`句。</span><span class="sxs-lookup"><span data-stu-id="fbf27-114">Follow the variable name with an `As` clause.</span></span>  
  
5. <span data-ttu-id="fbf27-115">に従って、`As`キーワードは、適切な複合データ型の名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="fbf27-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf27-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbf27-116">See also</span></span>

- [<span data-ttu-id="fbf27-117">データの種類</span><span class="sxs-lookup"><span data-stu-id="fbf27-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="fbf27-118">型文字</span><span class="sxs-lookup"><span data-stu-id="fbf27-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="fbf27-119">複合データ型</span><span class="sxs-lookup"><span data-stu-id="fbf27-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="fbf27-120">構造体</span><span class="sxs-lookup"><span data-stu-id="fbf27-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="fbf27-121">配列</span><span class="sxs-lookup"><span data-stu-id="fbf27-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="fbf27-122">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="fbf27-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="fbf27-123">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="fbf27-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
