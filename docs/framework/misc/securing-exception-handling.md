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
ms.openlocfilehash: e0465f2eb6be61e161f5e6b8cadf629a53f11906
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215786"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="88a99-102">例外処理の保護</span><span class="sxs-lookup"><span data-stu-id="88a99-102">Securing Exception Handling</span></span>
<span data-ttu-id="88a99-103">ビジュアルC++と Visual Basic では、スタックのさらに上にあるフィルター式は、 **finally**ステートメントの前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="88a99-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="88a99-104">このフィルターに関連付けられている**catch**ブロックは、 **finally**ステートメントの後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="88a99-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="88a99-105">詳細については、「[ユーザーフィルター例外の使用](../../standard/exceptions/using-user-filtered-exception-handlers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88a99-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="88a99-106">このセクションでは、この順序のセキュリティへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="88a99-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="88a99-107">次の擬似コード例は、フィルターステートメントと**finally**ステートメントの実行順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="88a99-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="88a99-108">このコードは、次を出力します。</span><span class="sxs-lookup"><span data-stu-id="88a99-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="88a99-109">このフィルターは、 **finally**ステートメントの前に実行されるので、他のコードの実行によって発生する可能性がある状態変更を行うすべてのものによって、セキュリティの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88a99-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="88a99-110">例 :</span><span class="sxs-lookup"><span data-stu-id="88a99-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="88a99-111">この擬似コードを使用すると、スタックの上位にあるフィルターで任意のコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="88a99-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="88a99-112">その他の操作の例としては、別の id の一時的な偽装、セキュリティチェックをバイパスする内部フラグの設定、またはスレッドに関連付けられているカルチャの変更などがあります。</span><span class="sxs-lookup"><span data-stu-id="88a99-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="88a99-113">推奨される解決方法は、コードの変更を呼び出し元のフィルターブロックからスレッド状態に分離する例外ハンドラーを導入することです。</span><span class="sxs-lookup"><span data-stu-id="88a99-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="88a99-114">ただし、例外ハンドラーが正しく導入されていること、またはこの問題が解決されないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="88a99-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="88a99-115">次の例では、UI カルチャを切り替えますが、あらゆる種類のスレッド状態変更が同様に公開される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88a99-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="88a99-116">この場合の適切な修正は、 **try**/**catch**ブロックで既存の**try**/**finally**ブロックをラップすることです。</span><span class="sxs-lookup"><span data-stu-id="88a99-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="88a99-117">次の例に示すように、 **catch throw**句を既存の**try**/**finally**ブロックに導入するだけでは問題は解決されません。</span><span class="sxs-lookup"><span data-stu-id="88a99-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="88a99-118">`FilterFunc` が制御を取得する前に**finally**ステートメントが実行されていないため、問題は解決されません。</span><span class="sxs-lookup"><span data-stu-id="88a99-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="88a99-119">次の例では、呼び出し元の例外フィルターブロックを例外として使用する前に**finally**句が実行されていることを確認して、問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="88a99-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88a99-120">参照</span><span class="sxs-lookup"><span data-stu-id="88a99-120">See also</span></span>

- [<span data-ttu-id="88a99-121">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="88a99-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
