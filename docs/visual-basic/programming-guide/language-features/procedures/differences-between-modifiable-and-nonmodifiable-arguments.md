---
title: 変更できる引数と変更できない引数の違い
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 733f92cc2cdaa6e923c57649774ceb64de172c18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403344"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="39f2c-102">変更できる引数と変更できない引数の違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39f2c-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="39f2c-103">プロシージャを呼び出す場合、通常は 1 つ以上の引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="39f2c-104">各引数は、基となるプログラミング要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="39f2c-105">基となる要素と引数自体のいずれも、変更可能な場合と変更不可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="39f2c-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="39f2c-106">変更可能な要素と変更不可能な要素</span><span class="sxs-lookup"><span data-stu-id="39f2c-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="39f2c-107">プログラミング要素は、値を変更できる "*変更可能な要素*"、または作成後は固定値を持つ "*変更不可能な要素*" のいずれかの場合があります。</span><span class="sxs-lookup"><span data-stu-id="39f2c-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="39f2c-108">次の表に、変更可能なプログラミング要素と変更不可能なプログラミング要素を示します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="39f2c-109">変更可能な要素</span><span class="sxs-lookup"><span data-stu-id="39f2c-109">Modifiable elements</span></span>|<span data-ttu-id="39f2c-110">変更不可能な要素</span><span class="sxs-lookup"><span data-stu-id="39f2c-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="39f2c-111">オブジェクト変数を含むローカル変数 (プロシージャ内で宣言) (読み取り専用を除く)</span><span class="sxs-lookup"><span data-stu-id="39f2c-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="39f2c-112">読み取り専用の変数、フィールド、プロパティ</span><span class="sxs-lookup"><span data-stu-id="39f2c-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="39f2c-113">フィールド (モジュール、クラス、構造体のメンバー変数) (読み取り専用を除く)</span><span class="sxs-lookup"><span data-stu-id="39f2c-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="39f2c-114">定数とリテラル</span><span class="sxs-lookup"><span data-stu-id="39f2c-114">Constants and literals</span></span>|  
|<span data-ttu-id="39f2c-115">プロパティ (読み取り専用を除く)</span><span class="sxs-lookup"><span data-stu-id="39f2c-115">Properties, except for read-only</span></span>|<span data-ttu-id="39f2c-116">列挙メンバー</span><span class="sxs-lookup"><span data-stu-id="39f2c-116">Enumeration members</span></span>|  
|<span data-ttu-id="39f2c-117">配列要素</span><span class="sxs-lookup"><span data-stu-id="39f2c-117">Array elements</span></span>|<span data-ttu-id="39f2c-118">式 (要素が変更可能な場合でも)</span><span class="sxs-lookup"><span data-stu-id="39f2c-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="39f2c-119">変更可能な引数と変更不可能な引数</span><span class="sxs-lookup"><span data-stu-id="39f2c-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="39f2c-120">"*変更可能な引数*" とは、基となる要素が変更可能なものです。</span><span class="sxs-lookup"><span data-stu-id="39f2c-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="39f2c-121">呼び出し元のコードにはいつでも新しい値を格納できます。引数 [ByRef](../../../language-reference/modifiers/byref.md) を渡すと、プロシージャのコードによって呼び出し元のコードの基となる要素を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="39f2c-122">"*変更不可能な引数*" には、変更不可能な基となる要素があるか、[ByVal](../../../language-reference/modifiers/byval.md) が渡されます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="39f2c-123">変更可能な要素であっても、プロシージャを使用して、呼び出し元のコードの基となる要素を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="39f2c-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="39f2c-124">変更不可能な要素の場合、呼び出し元のコード自体でそれを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="39f2c-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="39f2c-125">呼び出されたプロシージャによって、変更不可能な引数のローカル コピーを変更することはできますが、その変更は呼び出し元のコードの基となる要素には影響しません。</span><span class="sxs-lookup"><span data-stu-id="39f2c-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f2c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="39f2c-126">See also</span></span>

- [<span data-ttu-id="39f2c-127">手順</span><span class="sxs-lookup"><span data-stu-id="39f2c-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="39f2c-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="39f2c-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="39f2c-129">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="39f2c-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="39f2c-130">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="39f2c-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="39f2c-131">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="39f2c-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="39f2c-132">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="39f2c-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="39f2c-133">方法: プロシージャ引数の値が変更されないように保護する</span><span class="sxs-lookup"><span data-stu-id="39f2c-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="39f2c-134">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="39f2c-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="39f2c-135">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="39f2c-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="39f2c-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="39f2c-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
