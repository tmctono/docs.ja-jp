---
title: '方法: 引数の値渡しを強制する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 8261d126f988bdcf05b4a2af3106b38717e46bc8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344517"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="4198f-102">方法: 引数の値渡しを強制する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4198f-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="4198f-103">プロシージャの宣言によって、渡される機構が決まります。</span><span class="sxs-lookup"><span data-stu-id="4198f-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="4198f-104">パラメーターが[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)として宣言されている場合、Visual Basic は、対応する引数を参照渡しで渡すことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="4198f-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="4198f-105">これにより、プロシージャは、呼び出し元のコードの引数の基になるプログラミング要素の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4198f-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="4198f-106">このような変更に対して基になる要素を保護する場合は、引数名をかっこで囲むことによって、プロシージャ呼び出しの `ByRef` 渡す機構をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4198f-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="4198f-107">これらのかっこに加えて、呼び出しの引数リストを囲むかっこが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4198f-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="4198f-108">呼び出し元のコードで[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)機構をオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4198f-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="4198f-109">引数を強制的に値によって渡すには</span><span class="sxs-lookup"><span data-stu-id="4198f-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="4198f-110">対応するパラメーターがプロシージャの `ByVal` として宣言されている場合、追加の手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4198f-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="4198f-111">Visual Basic は、既に値渡しで引数を渡すことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="4198f-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="4198f-112">対応するパラメーターがプロシージャの `ByRef` として宣言されている場合は、プロシージャ呼び出しで引数をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="4198f-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4198f-113">例</span><span class="sxs-lookup"><span data-stu-id="4198f-113">Example</span></span>  
 <span data-ttu-id="4198f-114">次の例では、`ByRef` パラメーター宣言をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4198f-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="4198f-115">`ByVal`を強制する呼び出しで、2つのレベルのかっこに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4198f-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="4198f-116">`str` が引数リスト内の余分なかっこで囲まれている場合、`setNewString` プロシージャは呼び出し元のコードの値を変更できず、"ByVal が渡された場合は置き換えることができません" `MsgBox` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="4198f-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="4198f-117">`str` が余分なかっこで囲まれていない場合は、プロシージャによって変更され、"inString 引数の新しい値です" と表示さ `MsgBox` ます。</span><span class="sxs-lookup"><span data-stu-id="4198f-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4198f-118">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4198f-118">Compiling the Code</span></span>  
 <span data-ttu-id="4198f-119">変数を参照渡しで渡す場合は、`ByRef` キーワードを使用してこのメカニズムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4198f-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="4198f-120">Visual Basic の既定では、値渡しで引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="4198f-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="4198f-121">ただし、すべての宣言されたパラメーターに[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)キーワードまたは[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワードを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4198f-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="4198f-122">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4198f-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4198f-123">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="4198f-123">Robust Programming</span></span>  
 <span data-ttu-id="4198f-124">プロシージャが[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)パラメーターを宣言する場合、コードの正しい実行は、呼び出し元のコード内の基になる要素を変更できるかどうかに依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4198f-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="4198f-125">呼び出し元のコードが引数をかっこで囲むことによってこの呼び出し機構をオーバーライドした場合、または変更できない引数を渡した場合、プロシージャは基になる要素を変更できません。</span><span class="sxs-lookup"><span data-stu-id="4198f-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="4198f-126">これにより、呼び出し元のコードで予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4198f-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4198f-127">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4198f-127">.NET Framework Security</span></span>  
 <span data-ttu-id="4198f-128">プロシージャが呼び出し元のコードの引数の基になる値を変更できるようにすると、常にリスクが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4198f-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="4198f-129">この値が変更されることが予想されることを確認し、使用前に有効かどうかを確認できるように準備してください。</span><span class="sxs-lookup"><span data-stu-id="4198f-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4198f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4198f-130">See also</span></span>

- [<span data-ttu-id="4198f-131">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="4198f-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4198f-132">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="4198f-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4198f-133">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="4198f-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4198f-134">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="4198f-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4198f-135">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="4198f-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="4198f-136">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="4198f-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="4198f-137">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="4198f-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="4198f-138">方法: プロシージャ引数の値が変化しないようにする</span><span class="sxs-lookup"><span data-stu-id="4198f-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="4198f-139">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="4198f-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="4198f-140">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="4198f-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
