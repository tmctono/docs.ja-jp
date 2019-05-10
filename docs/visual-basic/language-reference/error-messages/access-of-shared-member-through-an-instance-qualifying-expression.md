---
title: インスタンスを経由する共有メンバーへのアクセスです。正規の式は評価されません。
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 311f4c025072162e0cfb6b87587f8602d33fcd19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646877"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="d5eb4-102">インスタンスを経由する共有メンバーへのアクセスです。正規の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="d5eb4-103">クラスまたは構造体のインスタンス変数を使用するアクセス、`Shared`変数、プロパティ、プロシージャ、またはそのクラスまたは構造体で定義されているイベント。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="d5eb4-104">この警告は、インスタンス変数をクラスまたは構造体、定数または列挙型、または入れ子になったクラスまたは構造体などの暗黙的な共有メンバーへのアクセスに使用する場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="d5eb4-105">メンバーの共有の目的は、そのメンバーのコピーが 1 つだけを作成し、その 1 つのコピーのクラスまたは構造体が宣言されているすべてのインスタンスを使用できるようにすること。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="d5eb4-106">アクセスするには、この目的で矛盾がある、`Shared`メンバーがそのクラスまたは構造体の個々 のインスタンスを保持する変数ではなく、クラスまたは構造の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="d5eb4-107">アクセス、`Shared`インスタンス変数によるメンバーが難しく、コード、メンバーであるという事実を隠すことで理解する`Shared`します。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="d5eb4-108">さらに、このようなアクセスが式の一部である場合、ように、他のアクションを実行するには`Function`共有メンバーのインスタンスを返すプロシージャでは、Visual Basic は、式とそれ以外の場合、その他のアクションをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="d5eb4-109">詳細と例では、次を参照してください。 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="d5eb4-110">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-110">By default, this message is a warning.</span></span> <span data-ttu-id="d5eb4-111">警告を表示しない方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d5eb4-112">**エラー ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="d5eb4-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5eb4-113">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d5eb4-113">To correct this error</span></span>  
  
- <span data-ttu-id="d5eb4-114">クラスまたは定義する構造体の名前を使用して、`Shared`に次の例に示すように、アクセスするメンバー。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="d5eb4-115">2 つのプログラミング要素が同じ名前を持つ場合は、スコープの影響についてアラートが。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="d5eb4-116">使用してインスタンスを宣言する場合、前の例で`Dim testClass as testClass = Nothing`、コンパイラを呼び出す`testClass.sayHello()`クラス名、および警告なしでメソッドのアクセスが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="d5eb4-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5eb4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5eb4-117">See also</span></span>

- [<span data-ttu-id="d5eb4-118">Shared</span><span class="sxs-lookup"><span data-stu-id="d5eb4-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="d5eb4-119">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="d5eb4-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
