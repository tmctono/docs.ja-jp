---
title: スレッドを作成し、開始時にデータを渡す
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: a628cbb4c9ec8e1c9ccd9fd73e72a82ecf2b2836
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138103"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="fc4dd-102">スレッドを作成し、開始時にデータを渡す</span><span class="sxs-lookup"><span data-stu-id="fc4dd-102">Creating threads and passing data at start time</span></span>

<span data-ttu-id="fc4dd-103">オペレーティング システム プロセスが作成されると、オペレーティング システムは、元のアプリケーション ドメインを含め、そのプロセスでコードを実行するスレッドを挿入します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="fc4dd-104">その時点から、オペレーティング システム スレッドを作成または破棄せずに、アプリケーション ドメインを作成したり破棄したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="fc4dd-105">実行対象コードがマネージド コードである場合は、<xref:System.Threading.Thread> 型の静的 <xref:System.Threading.Thread.CurrentThread%2A> プロパティを取得することで、現在のアプリケーション ドメインで実行されるスレッドの <xref:System.Threading.Thread> オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="fc4dd-106">このトピックではスレッドの作成について説明し、データをスレッド プロシージャに渡すための代替手段について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="fc4dd-107">スレッドの作成</span><span class="sxs-lookup"><span data-stu-id="fc4dd-107">Creating a thread</span></span>

 <span data-ttu-id="fc4dd-108">新しい <xref:System.Threading.Thread> オブジェクトを作成すると、新しいマネージド スレッドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="fc4dd-109"><xref:System.Threading.Thread> クラスには <xref:System.Threading.ThreadStart> デリゲートまたは <xref:System.Threading.ParameterizedThreadStart> デリゲートを受け取るコンストラクターがあります。デリゲートは、<xref:System.Threading.Thread.Start%2A> メソッドの呼び出し時に新しいスレッドで呼び出されるメソッドをラップします。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="fc4dd-110">複数回 <xref:System.Threading.Thread.Start%2A> を呼び出すと、<xref:System.Threading.ThreadStateException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="fc4dd-111"><xref:System.Threading.Thread.Start%2A> メソッドはすぐに (多くの場合、新しいスレッドが実際に開始される前) 制御を返します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="fc4dd-112"><xref:System.Threading.Thread.ThreadState%2A> および <xref:System.Threading.Thread.IsAlive%2A> プロパティを使用して、任意の時点のスレッドの状態を判別できますが、スレッドのアクティビティを同期する場合にこれらのプロパティを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc4dd-113">スレッドが開始された後に、<xref:System.Threading.Thread> オブジェクトへの参照を保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="fc4dd-114">スレッドは、スレッド プロシージャが終了するまで、引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="fc4dd-115">次のコード例では、2 つの新しいスレッドを作成し、別のオブジェクトでインスタンスおよび静的メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a><span data-ttu-id="fc4dd-116">データをスレッドに渡す</span><span class="sxs-lookup"><span data-stu-id="fc4dd-116">Passing data to threads</span></span>

 <span data-ttu-id="fc4dd-117">.NET framework Version 2.0 では、<xref:System.Threading.ParameterizedThreadStart> デリゲートは、<xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> メソッド オーバーロードの呼び出し時にスレッドにデータを含むオブジェクトを渡すための簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="fc4dd-118">コード例については、「<xref:System.Threading.ParameterizedThreadStart>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="fc4dd-119"><xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> メソッド オーバーロードではすべてのオブジェクトを受け入れるため、<xref:System.Threading.ParameterizedThreadStart> デリゲートの使用はデータを渡すためのタイプ セーフな方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="fc4dd-120">代わりに、ヘルパー クラスにデータとスレッド プロシージャをカプセル化し、<xref:System.Threading.ThreadStart> デリゲートを使用して、スレッド プロシージャを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="fc4dd-121">この手法を示す例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-121">The following example demonstrates this technique:</span></span>

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

<span data-ttu-id="fc4dd-122">非同期呼び出しからデータを返す場所がないため、<xref:System.Threading.ThreadStart> と <xref:System.Threading.ParameterizedThreadStart> のどちらのデリゲートにも戻り値がありません。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-122">Neither <xref:System.Threading.ThreadStart> nor <xref:System.Threading.ParameterizedThreadStart> delegate has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="fc4dd-123">スレッド メソッドの結果を取得するために、コールバック メソッドを使用することができます。これについては、次のセクションに示されています。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-123">To retrieve the results of a thread method, you can use a callback method, as shown in the next section.</span></span>
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a><span data-ttu-id="fc4dd-124">コールバック メソッドによるスレッドからのデータの取得</span><span class="sxs-lookup"><span data-stu-id="fc4dd-124">Retrieving data from threads with callback methods</span></span>

 <span data-ttu-id="fc4dd-125">次の例では、スレッドからデータを取得するコールバック メソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="fc4dd-126">データとスレッド メソッドを含むクラスのコンストラクターは、コールバック メソッドを表すデリゲートも受け入れます。スレッド メソッドが終了する前に、コールバック デリゲートが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fc4dd-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fc4dd-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc4dd-127">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fc4dd-128">スレッド化</span><span class="sxs-lookup"><span data-stu-id="fc4dd-128">Threading</span></span>](index.md)
- [<span data-ttu-id="fc4dd-129">スレッドの使用とスレッド処理</span><span class="sxs-lookup"><span data-stu-id="fc4dd-129">Using Threads and Threading</span></span>](using-threads-and-threading.md)
