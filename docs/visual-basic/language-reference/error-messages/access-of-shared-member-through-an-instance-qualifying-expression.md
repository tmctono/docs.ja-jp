---
title: インスタンスを経由する共有メンバーへのアクセスです。正規の式は評価されません。
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947696"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="718b9-102">インスタンスを経由する共有メンバーへのアクセスです。正規の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="718b9-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="718b9-103">クラスまたは構造体のインスタンス変数は、そのクラスまた`Shared`は構造体で定義されている変数、プロパティ、プロシージャ、またはイベントにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="718b9-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="718b9-104">この警告は、クラスまたは構造体の暗黙的に共有されるメンバー (定数、列挙型、または入れ子になったクラスまたは構造体) へのアクセスにインスタンス変数が使用されている場合にも発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="718b9-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="718b9-105">メンバーを共有する目的は、そのメンバーのコピーを1つだけ作成し、そのコピーを、宣言されているクラスまたは構造体のすべてのインスタンスで使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="718b9-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="718b9-106">クラスまたは構造体の個々のインスタンス`Shared`を保持する変数ではなく、クラスまたは構造体の名前を使用してメンバーにアクセスするために、この目的と一貫性があります。</span><span class="sxs-lookup"><span data-stu-id="718b9-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="718b9-107">インスタンス変数を使用して`Shared`メンバーにアクセスすると、メンバーがであるという事実を隠ぺいすることで、コードを理解しづらくなる可能性があります。`Shared`</span><span class="sxs-lookup"><span data-stu-id="718b9-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="718b9-108">さらに、このようなアクセスが、共有メンバーのインスタンスを返す`Function`プロシージャなど、他のアクションを実行する式の一部である場合、Visual Basic は式およびそれ以外で実行されるその他のアクションをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="718b9-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="718b9-109">詳細と例については、「[共有](../../../visual-basic/language-reference/modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="718b9-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="718b9-110">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="718b9-110">By default, this message is a warning.</span></span> <span data-ttu-id="718b9-111">警告を表示しない方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="718b9-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="718b9-112">**エラー ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="718b9-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="718b9-113">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="718b9-113">To correct this error</span></span>  
  
- <span data-ttu-id="718b9-114">次の例に示すように、アクセスする`Shared`メンバーを定義するクラスまたは構造体の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="718b9-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="718b9-115">2つのプログラミング要素が同じ名前の場合に、スコープの効果に関する警告を出します。</span><span class="sxs-lookup"><span data-stu-id="718b9-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="718b9-116">前の例では、を使用`Dim testClass as testClass = Nothing`してインスタンスを宣言する場合、コンパイラはの`testClass.sayHello()`呼び出しをクラス名を通じてメソッドのアクセスとして処理しますが、警告は発生しません。</span><span class="sxs-lookup"><span data-stu-id="718b9-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="718b9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="718b9-117">See also</span></span>

- [<span data-ttu-id="718b9-118">Shared</span><span class="sxs-lookup"><span data-stu-id="718b9-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="718b9-119">Visual Basic 内のスコープ</span><span class="sxs-lookup"><span data-stu-id="718b9-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
