---
title: 例外処理の保護
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: ad27e62197f6fdaa6b5e706f4ae02c03fecae9f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181137"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="3825f-102">例外処理の保護</span><span class="sxs-lookup"><span data-stu-id="3825f-102">Securing Exception Handling</span></span>
<span data-ttu-id="3825f-103">Visual C++ および Visual Basic では、フィルター式が、最終的**なステートメント**の前に、スタックの上方に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3825f-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="3825f-104">そのフィルターに関連付けられた**catch**ブロックは **、finally**ステートメントの後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3825f-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="3825f-105">詳細については、「[ユーザーフィルター処理例外の使用](../../standard/exceptions/using-user-filtered-exception-handlers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3825f-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="3825f-106">このセクションでは、この順序のセキュリティへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="3825f-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="3825f-107">フィルター ステートメントと**finally**ステートメントの実行順序を示す次の擬似コード例を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3825f-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()
{  
    try
    {  
        Sub();  
    }
    except (Filter())
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()
{  
    try
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }
    finally
    {  
        Console.WriteLine("finally");  
    }  
}
```  
  
 <span data-ttu-id="3825f-108">このコードは、次のコードを出力します。</span><span class="sxs-lookup"><span data-stu-id="3825f-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="3825f-109">フィルターは**finally**ステートメントの前に実行されるため、他のコードの実行が利用できる状態の変更を行う何かによってセキュリティの問題を導入できます。</span><span class="sxs-lookup"><span data-stu-id="3825f-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="3825f-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3825f-110">For example:</span></span>  
  
```cpp  
try
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and
    // so on) that could be exploited if malicious
    // code ran before state is restored.  
    Do_some_work();  
}
finally
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="3825f-111">この擬似コードを使用すると、スタックの上位にあるフィルタで任意のコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3825f-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="3825f-112">同様の効果を持つ操作の他の例としては、別の ID の一時的な偽装、セキュリティ チェックをバイパスする内部フラグの設定、またはスレッドに関連付けられたカルチャの変更があります。</span><span class="sxs-lookup"><span data-stu-id="3825f-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="3825f-113">推奨される解決策は、例外ハンドラーを導入して、コードのスレッド状態への変更を呼び出し元のフィルター ブロックから分離することです。</span><span class="sxs-lookup"><span data-stu-id="3825f-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="3825f-114">ただし、例外ハンドラが適切に導入されているか、この問題が解決されないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="3825f-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="3825f-115">次の例では、UI カルチャを切り替えますが、スレッド状態の変更の種類は同様に公開できます。</span><span class="sxs-lookup"><span data-stu-id="3825f-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="3825f-116">この場合の修正は、既存の**try**/**finally**ブロックを**try**/**catch**ブロックにラップする方法です。</span><span class="sxs-lookup"><span data-stu-id="3825f-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="3825f-117">次の例に示すように **、catch-throw**句を既存の**try**/**finally**ブロックに導入するだけでは問題は解決しません。</span><span class="sxs-lookup"><span data-stu-id="3825f-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="3825f-118">finally**ステートメントが**制御を取得する前に実行されていないため、この方法`FilterFunc`では問題は解決しません。</span><span class="sxs-lookup"><span data-stu-id="3825f-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="3825f-119">次の例では、呼び出し元の例外フィルター ブロックを例外を提供する前に**finally**句が実行されたことを確認することで、問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="3825f-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try
    {  
        try
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3825f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3825f-120">See also</span></span>

- [<span data-ttu-id="3825f-121">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3825f-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
