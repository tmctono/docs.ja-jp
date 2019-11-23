---
title: 式は、含んでいるプロパティ '<propertyname>' を再帰的に呼び出します。
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698567"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="521c4-102">式は、含んでいるプロパティ '\<propertyname > ' を再帰的に呼び出します</span><span class="sxs-lookup"><span data-stu-id="521c4-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="521c4-103">プロパティ定義の `Set` プロシージャ内のステートメントは、プロパティの名前に値を格納します。</span><span class="sxs-lookup"><span data-stu-id="521c4-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="521c4-104">プロパティの値を保持するには、プロパティのコンテナーで `Private` 変数を定義し、`Get` と `Set` の両方のプロシージャで使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="521c4-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="521c4-105">`Set` プロシージャは、この `Private` 変数に入力値を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="521c4-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="521c4-106">`Get` プロシージャは、`Function` プロシージャと同じように動作するので、`End Get` ステートメントを使用して、プロパティ名に値を割り当て、制御を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="521c4-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="521c4-107">ただし、`Private` 変数を[Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)の値として含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="521c4-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="521c4-108">`Set` プロシージャは、値を返さない `Sub` プロシージャと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="521c4-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="521c4-109">したがって、プロシージャまたはプロパティの名前は `Set` プロシージャ内で特別な意味を持たず、値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="521c4-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="521c4-110">次の例では、このエラーの原因となる可能性がある方法を示し、その後に推奨される方法を示します。</span><span class="sxs-lookup"><span data-stu-id="521c4-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="521c4-111">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="521c4-111">By default, this message is a warning.</span></span> <span data-ttu-id="521c4-112">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="521c4-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="521c4-113">**エラー ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="521c4-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="521c4-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="521c4-114">To correct this error</span></span>  
  
- <span data-ttu-id="521c4-115">前の例に示されているように、推奨される方法を使用するようにプロパティ定義を書き直してください。</span><span class="sxs-lookup"><span data-stu-id="521c4-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521c4-116">参照</span><span class="sxs-lookup"><span data-stu-id="521c4-116">See also</span></span>

- [<span data-ttu-id="521c4-117">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="521c4-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="521c4-118">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="521c4-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="521c4-119">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="521c4-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
