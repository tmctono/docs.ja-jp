---
title: プロパティ '<propertyname>' は、すべてのコードのパスでは値を返しません。
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: a535a6b951dc9872109527f78d7de5f3fcdd3292
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971645"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="c39fb-102">プロパティ '\<propertyname >' は、すべてのコード パスで値を返しません</span><span class="sxs-lookup"><span data-stu-id="c39fb-102">Property '\<propertyname>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="c39fb-103">プロパティ '\<propertyname >' は、すべてのコード パスで値を返しません。</span><span class="sxs-lookup"><span data-stu-id="c39fb-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="c39fb-104">この結果が使用されると、実行時に Null 参照例外が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c39fb-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="c39fb-105">プロパティ`Get`手順では、値を返さないコードの少なくとも 1 つの可能なパス。</span><span class="sxs-lookup"><span data-stu-id="c39fb-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="c39fb-106">プロパティから値を返すことができます`Get`次の方法のいずれかの手順。</span><span class="sxs-lookup"><span data-stu-id="c39fb-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="c39fb-107">プロパティ名に値を代入し、実行、`Exit Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="c39fb-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
- <span data-ttu-id="c39fb-108">プロパティ名に値を代入し、実行、`End Get`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="c39fb-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
- <span data-ttu-id="c39fb-109">値を含める、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="c39fb-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="c39fb-110">コントロールに渡します`Exit Property`または`End Get`プロパティ名の後に任意の値が割り当てられていないと、`Get`プロパティのデータ型の既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="c39fb-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="c39fb-111">詳細については、「動作」を参照してください[関数ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="c39fb-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="c39fb-112">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="c39fb-112">By default, this message is a warning.</span></span> <span data-ttu-id="c39fb-113">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c39fb-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c39fb-114">**エラー ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="c39fb-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c39fb-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c39fb-115">To correct this error</span></span>  
  
- <span data-ttu-id="c39fb-116">制御フローのロジックを確認し、すべてが値を返すステートメントの前に値を代入するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c39fb-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="c39fb-117">常に使用する場合に、プロシージャからリターンごとに値を返すことを保証する方が簡単、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="c39fb-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="c39fb-118">この場合、最後のステートメントの前に`End Get`する必要があります、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="c39fb-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39fb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c39fb-119">See also</span></span>

- [<span data-ttu-id="c39fb-120">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c39fb-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="c39fb-121">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="c39fb-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="c39fb-122">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="c39fb-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
