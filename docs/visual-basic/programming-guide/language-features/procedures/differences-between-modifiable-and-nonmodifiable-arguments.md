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
ms.openlocfilehash: 989795ee2cdd3a78b71bad4d95cf9b384c2719bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341387"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="378f0-102">変更できる引数と変更できない引数の違い (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="378f0-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="378f0-103">プロシージャを呼び出す場合、通常は1つ以上の引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="378f0-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="378f0-104">各引数は、基になるプログラミング要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="378f0-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="378f0-105">基になる要素と引数自体の両方を変更可能または変更できません。</span><span class="sxs-lookup"><span data-stu-id="378f0-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="378f0-106">変更可能な要素と変更不可能な要素</span><span class="sxs-lookup"><span data-stu-id="378f0-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="378f0-107">プログラミング要素には、変更可能な*要素*(値を変更することができます)、または作成後に固定値を持つ変更でき*ない要素の*いずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="378f0-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="378f0-108">次の表に、変更可能なプログラミング要素と変更できないプログラミング要素の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="378f0-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="378f0-109">変更可能な要素</span><span class="sxs-lookup"><span data-stu-id="378f0-109">Modifiable elements</span></span>|<span data-ttu-id="378f0-110">不変の要素</span><span class="sxs-lookup"><span data-stu-id="378f0-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="378f0-111">ローカル変数 (プロシージャ内で宣言されます)。読み取り専用を除き、オブジェクト変数を含みます。</span><span class="sxs-lookup"><span data-stu-id="378f0-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="378f0-112">読み取り専用の変数、フィールド、およびプロパティ</span><span class="sxs-lookup"><span data-stu-id="378f0-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="378f0-113">フィールド (モジュール、クラス、および構造体のメンバー変数) (読み取り専用を除く)</span><span class="sxs-lookup"><span data-stu-id="378f0-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="378f0-114">定数とリテラル</span><span class="sxs-lookup"><span data-stu-id="378f0-114">Constants and literals</span></span>|  
|<span data-ttu-id="378f0-115">プロパティ (読み取り専用を除く)</span><span class="sxs-lookup"><span data-stu-id="378f0-115">Properties, except for read-only</span></span>|<span data-ttu-id="378f0-116">列挙型のメンバー</span><span class="sxs-lookup"><span data-stu-id="378f0-116">Enumeration members</span></span>|  
|<span data-ttu-id="378f0-117">配列要素</span><span class="sxs-lookup"><span data-stu-id="378f0-117">Array elements</span></span>|<span data-ttu-id="378f0-118">式 (要素が変更可能な場合でも)</span><span class="sxs-lookup"><span data-stu-id="378f0-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="378f0-119">変更可能な引数と変更不可能な引数</span><span class="sxs-lookup"><span data-stu-id="378f0-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="378f0-120">変更可能な*引数*は、変更可能な基になる要素を持つものです。</span><span class="sxs-lookup"><span data-stu-id="378f0-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="378f0-121">呼び出し元のコードは、新しい値をいつでも格納できます。引数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)を渡すと、プロシージャ内のコードは、呼び出し元のコード内の基になる要素を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="378f0-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="378f0-122">*不変の引数*は、基になる要素が不変であるか、または[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)で渡されています。</span><span class="sxs-lookup"><span data-stu-id="378f0-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="378f0-123">プロシージャは、変更可能な要素であっても、呼び出し元のコード内の基になる要素を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="378f0-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="378f0-124">変更できない要素の場合は、呼び出し元のコード自体が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="378f0-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="378f0-125">呼び出されたプロシージャは、変更できない引数のローカルコピーを変更する場合がありますが、その変更は呼び出し元のコードの基になる要素に影響しません。</span><span class="sxs-lookup"><span data-stu-id="378f0-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378f0-126">参照</span><span class="sxs-lookup"><span data-stu-id="378f0-126">See also</span></span>

- [<span data-ttu-id="378f0-127">手順</span><span class="sxs-lookup"><span data-stu-id="378f0-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="378f0-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="378f0-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="378f0-129">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="378f0-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="378f0-130">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="378f0-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="378f0-131">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="378f0-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="378f0-132">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="378f0-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="378f0-133">方法: プロシージャ引数の値が変化しないようにする</span><span class="sxs-lookup"><span data-stu-id="378f0-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="378f0-134">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="378f0-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="378f0-135">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="378f0-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="378f0-136">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="378f0-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
