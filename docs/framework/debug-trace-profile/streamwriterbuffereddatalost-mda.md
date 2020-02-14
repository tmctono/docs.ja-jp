---
title: streamWriterBufferedDataLost MDA
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
ms.openlocfilehash: 82940b40b302f4a928547f2e6a0c285727e13934
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216096"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="80e53-102">streamWriterBufferedDataLost MDA</span><span class="sxs-lookup"><span data-stu-id="80e53-102">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="80e53-103">`streamWriterBufferedDataLost` マネージド デバッグ アシスタント (MDA) は <xref:System.IO.StreamWriter> が書き込まれたときに起動しますが、その後、<xref:System.IO.StreamWriter.Flush%2A> のインスタンスが破棄される前に <xref:System.IO.StreamWriter.Close%2A> または <xref:System.IO.StreamWriter> メソッドが呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="80e53-103">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="80e53-104">この MDA が有効になると、バッファーに入れられたデータが <xref:System.IO.StreamWriter> 内に残っているか、ランタイムにより判断されます。</span><span class="sxs-lookup"><span data-stu-id="80e53-104">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="80e53-105">バッファーに入れられたデータが残っている場合、MDA が起動します。</span><span class="sxs-lookup"><span data-stu-id="80e53-105">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="80e53-106"><xref:System.GC.Collect%2A> メソッドと <xref:System.GC.WaitForPendingFinalizers%2A> メソッドを呼び出すことで、ファイナライザーを強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="80e53-106">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="80e53-107">それ以外の場合、ファイナライザーは任意のタイミングで実行されます。プロセス終了時に実行されることは、ほぼありません。</span><span class="sxs-lookup"><span data-stu-id="80e53-107">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="80e53-108">この MDA が有効になっている状態でファイナライザーを明示的に実行すると、この種類の問題をより確実に再現できます。</span><span class="sxs-lookup"><span data-stu-id="80e53-108">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="80e53-109">現象</span><span class="sxs-lookup"><span data-stu-id="80e53-109">Symptoms</span></span>  
 <span data-ttu-id="80e53-110"><xref:System.IO.StreamWriter> では、最後の 1 – 4 KB のデータがファイルに書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="80e53-110">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="80e53-111">原因</span><span class="sxs-lookup"><span data-stu-id="80e53-111">Cause</span></span>  
 <span data-ttu-id="80e53-112"><xref:System.IO.StreamWriter> はデータを内部でバッファーに入れます。このとき、<xref:System.IO.StreamWriter.Close%2A> または <xref:System.IO.StreamWriter.Flush%2A> メソッドを呼び出し、バッファーに入れたデータを基礎となるデータ ストアに書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="80e53-112">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="80e53-113"><xref:System.IO.StreamWriter.Close%2A> または <xref:System.IO.StreamWriter.Flush%2A> が正しく呼び出されない場合、<xref:System.IO.StreamWriter> インスタンスのバッファーに入れられたデータは予想どおりに書き込まれないことがあります。</span><span class="sxs-lookup"><span data-stu-id="80e53-113">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="80e53-114">次は、この MDA がキャッチする、書き込みが十分ではないコードの例です。</span><span class="sxs-lookup"><span data-stu-id="80e53-114">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="80e53-115">開始したガベージ コレクションがファイナライザーの完了まで保留となる場合、先行のコードがこの MDA をより確実に起動します。</span><span class="sxs-lookup"><span data-stu-id="80e53-115">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="80e53-116">この種類の問題を追跡するために、デバッグ ビルドで、先行メソッドの終わりに次のコードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="80e53-116">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="80e53-117">これで MDA が起動する確率が高くなりますが、もちろん、問題の根本原因が解消されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="80e53-117">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="80e53-118">解決策</span><span class="sxs-lookup"><span data-stu-id="80e53-118">Resolution</span></span>  
 <span data-ttu-id="80e53-119">アプリケーションを閉じる前に、あるいは、<xref:System.IO.StreamWriter.Close%2A> のインスタンスが含まれるコード ブロックを終了する前に、<xref:System.IO.StreamWriter.Flush%2A> で <xref:System.IO.StreamWriter> または <xref:System.IO.StreamWriter> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="80e53-119">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="80e53-120">これを最も効率的に行う方法は、C# `using` ブロック (Visual Basic の場合、`Using`) でインスタンスを作成することです。ライターの <xref:System.IO.StreamWriter.Dispose%2A> メソッドが呼び出され、インスタンスが正しく終了します。</span><span class="sxs-lookup"><span data-stu-id="80e53-120">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="80e53-121">次のコードは同じ解決策ですが、`try/finally` の代わりに `using` が使用されています。</span><span class="sxs-lookup"><span data-stu-id="80e53-121">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
```csharp
StreamWriter sw;  
try   
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally   
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 <span data-ttu-id="80e53-122">いずれの解決策も利用できない場合 (<xref:System.IO.StreamWriter> が静的変数に保存されており、その有効期間の終わりにコードを実行することが簡単でない場合など)、最後に使用した後で <xref:System.IO.StreamWriter.Flush%2A> で <xref:System.IO.StreamWriter> を呼び出すか、最初に使用する前に <xref:System.IO.StreamWriter.AutoFlush%2A> プロパティを `true` に設定すると、この問題を解決できるはずです。</span><span class="sxs-lookup"><span data-stu-id="80e53-122">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()   
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="80e53-123">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="80e53-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="80e53-124">この MDA は、ランタイムに影響しません。</span><span class="sxs-lookup"><span data-stu-id="80e53-124">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="80e53-125">出力</span><span class="sxs-lookup"><span data-stu-id="80e53-125">Output</span></span>  
 <span data-ttu-id="80e53-126">この違反が発生したことを示すメッセージ</span><span class="sxs-lookup"><span data-stu-id="80e53-126">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="80e53-127">構成</span><span class="sxs-lookup"><span data-stu-id="80e53-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80e53-128">参照</span><span class="sxs-lookup"><span data-stu-id="80e53-128">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="80e53-129">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="80e53-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
