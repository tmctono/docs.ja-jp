---
title: CLS 準拠でない例外をキャッチする方法
description: CLS に準拠していない例外をキャッチする方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 255de4cab9a72491eb3b9624d968539d432e0442
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302010"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="57543-104">CLS 準拠でない例外をキャッチする方法</span><span class="sxs-lookup"><span data-stu-id="57543-104">How to catch a non-CLS exception</span></span>
<span data-ttu-id="57543-105">C++/CLI をはじめとする一部の .NET 言語では、<xref:System.Exception> から派生していない例外をオブジェクトでスローすることができます。</span><span class="sxs-lookup"><span data-stu-id="57543-105">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="57543-106">このような例外は "*CLS 準拠でない例外*" や "*非例外*" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="57543-106">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="57543-107">C# では、CLS 準拠でない例外をスローすることはできませんが、それらをキャッチすることはできます。次の 2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="57543-107">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="57543-108">`catch (RuntimeWrappedException e)` ブロック内で。</span><span class="sxs-lookup"><span data-stu-id="57543-108">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="57543-109">Visual C# アセンブリの既定の動作上、CLS 準拠でない例外はラップされた例外としてキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="57543-109">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="57543-110">元の例外にアクセスする必要がある場合 (<xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> プロパティからアクセスできます)、このメソッドを利用します。</span><span class="sxs-lookup"><span data-stu-id="57543-110">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="57543-111">この方法で例外をキャッチする方法については、このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="57543-111">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="57543-112">他のすべての `catch` ブロックの後に置いた汎用的な catch ブロック (例外の型が指定されていない catch ブロック) 内で。</span><span class="sxs-lookup"><span data-stu-id="57543-112">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="57543-113">この方法は、CLS 準拠でない例外への応答として何らかのアクション (ログ ファイルへの書き込みなど) を実行したい場合で、なおかつ例外情報にアクセスする必要がない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="57543-113">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="57543-114">既定では、すべての例外が共通言語ランタイムによってラップされます。</span><span class="sxs-lookup"><span data-stu-id="57543-114">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="57543-115">この動作を無効にするには、`[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]` というアセンブリ レベルの属性を (通常、AssemblyInfo.cs ファイル内の) コードに追加します。</span><span class="sxs-lookup"><span data-stu-id="57543-115">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="57543-116">CLS 準拠でない例外をキャッチするには</span><span class="sxs-lookup"><span data-stu-id="57543-116">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="57543-117">`catch(RuntimeWrappedException e)` ブロック内で、<xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> プロパティから元の例外にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="57543-117">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57543-118">例</span><span class="sxs-lookup"><span data-stu-id="57543-118">Example</span></span>  
 <span data-ttu-id="57543-119">次の例では、C++/CLI で記述されたクラス ライブラリからスローされた、CLS 準拠でない例外をキャッチする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57543-119">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="57543-120">この例で、C# クライアント コードは、スローされる例外の型が <xref:System.String?displayProperty=nameWithType> であることを事前に把握しています。</span><span class="sxs-lookup"><span data-stu-id="57543-120">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="57543-121">その型にコードからアクセスできる限り、<xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> プロパティは元の型にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="57543-121">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="57543-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="57543-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="57543-123">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="57543-123">Exceptions and Exception Handling</span></span>](./index.md)
