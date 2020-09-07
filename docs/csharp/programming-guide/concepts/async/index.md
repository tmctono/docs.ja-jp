---
title: C# での非同期プログラミング
description: C# 言語での async、await、Task、Task<T> を使用した非同期プログラミングのサポートの概要です
ms.date: 06/04/2020
ms.openlocfilehash: 853019c39880b1f4ef6536aed5841ecab53d7304
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414982"
---
# <a name="asynchronous-programming-with-async-and-await"></a><span data-ttu-id="14089-103">async および await を使用した非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="14089-103">Asynchronous programming with async and await</span></span>

<span data-ttu-id="14089-104">[タスク非同期プログラミング モデル (TAP)](task-asynchronous-programming-model.md) では、非同期コードに対する抽象化が提供されます。</span><span class="sxs-lookup"><span data-stu-id="14089-104">The [Task asynchronous programming model (TAP)](task-asynchronous-programming-model.md) provides an abstraction over asynchronous code.</span></span> <span data-ttu-id="14089-105">コードは、通常と同じようにステートメントのシーケンスとして記述します。</span><span class="sxs-lookup"><span data-stu-id="14089-105">You write code as a sequence of statements, just like always.</span></span> <span data-ttu-id="14089-106">次のステートメントが始まる前に、各ステートメントが完了するものとして、コードを読むことができます。</span><span class="sxs-lookup"><span data-stu-id="14089-106">You can read that code as though each statement completes before the next begins.</span></span> <span data-ttu-id="14089-107">これらのステートメントの一部は処理を開始し、進行中の作業を表す <xref:System.Threading.Tasks.Task> を返す可能性があるので、コンパイラではいくつかの変換が実行されます。</span><span class="sxs-lookup"><span data-stu-id="14089-107">The compiler performs a number of transformations because some of those statements may start work and return a <xref:System.Threading.Tasks.Task> that represents the ongoing work.</span></span>

<span data-ttu-id="14089-108">それがこの構文の目的です。コードは、順番に実行されるステートメントのように書かれていますが、外部リソースの割り当てとタスク完了のタイミングに基づいて、はるかに複雑な順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="14089-108">That's the goal of this syntax: enable code that reads like a sequence of statements, but executes in a much more complicated order based on external resource allocation and when tasks complete.</span></span> <span data-ttu-id="14089-109">それは、人が非同期のタスクを含むプロセスの指示を与えるのと似ています。</span><span class="sxs-lookup"><span data-stu-id="14089-109">It's analogous to how people give instructions for processes that include asynchronous tasks.</span></span> <span data-ttu-id="14089-110">この記事では、朝食を作る手順を例として使用し、`async` キーワードと `await` キーワードによって、一連の非同期命令を含むコードがどのように理解しやすくなるのかを見ていきます。</span><span class="sxs-lookup"><span data-stu-id="14089-110">Throughout this article, you'll use an example of instructions for making a breakfast to see how the `async` and `await` keywords make it easier to reason about code, that includes a series of asynchronous instructions.</span></span> <span data-ttu-id="14089-111">朝食を作る方法について説明する次の一覧のような手順を作成します。</span><span class="sxs-lookup"><span data-stu-id="14089-111">You'd write the instructions something like the following list to explain how to make a breakfast:</span></span>

1. <span data-ttu-id="14089-112">コーヒーをカップに注ぐ。</span><span class="sxs-lookup"><span data-stu-id="14089-112">Pour a cup of coffee.</span></span>
1. <span data-ttu-id="14089-113">フライパンを熱し、卵を 2 個焼く。</span><span class="sxs-lookup"><span data-stu-id="14089-113">Heat up a pan, then fry two eggs.</span></span>
1. <span data-ttu-id="14089-114">ベーコンを 3 切れ焼く。</span><span class="sxs-lookup"><span data-stu-id="14089-114">Fry three slices of bacon.</span></span>
1. <span data-ttu-id="14089-115">パンを 2 枚焼く。</span><span class="sxs-lookup"><span data-stu-id="14089-115">Toast two pieces of bread.</span></span>
1. <span data-ttu-id="14089-116">トーストにバターとジャムを塗る。</span><span class="sxs-lookup"><span data-stu-id="14089-116">Add butter and jam to the toast.</span></span>
1. <span data-ttu-id="14089-117">オレンジ ジュースをグラスに注ぐ。</span><span class="sxs-lookup"><span data-stu-id="14089-117">Pour a glass of orange juice.</span></span>

<span data-ttu-id="14089-118">料理の経験があれば、これらの手順を**非同期的に**実行するでしょう。</span><span class="sxs-lookup"><span data-stu-id="14089-118">If you have experience with cooking, you'd execute those instructions **asynchronously**.</span></span> <span data-ttu-id="14089-119">卵用のフライパンを熱し始めてから、ベーコンを始めます。</span><span class="sxs-lookup"><span data-stu-id="14089-119">You'd start warming the pan for eggs, then start the bacon.</span></span> <span data-ttu-id="14089-120">トースターにパンを入れたら、卵を焼き始めます。</span><span class="sxs-lookup"><span data-stu-id="14089-120">You'd put the bread in the toaster, then start the eggs.</span></span> <span data-ttu-id="14089-121">プロセスの各ステップで、あるタスクを開始したら、準備ができているタスクに注意を向けます。</span><span class="sxs-lookup"><span data-stu-id="14089-121">At each step of the process, you'd start a task, then turn your attention to tasks that are ready for your attention.</span></span>

<span data-ttu-id="14089-122">朝食の準備は、並列ではない非同期作業のよい例です。</span><span class="sxs-lookup"><span data-stu-id="14089-122">Cooking breakfast is a good example of asynchronous work that isn't parallel.</span></span> <span data-ttu-id="14089-123">1 人 (つまり 1 つのスレッド) で、これらすべてのタスクを処理できます。</span><span class="sxs-lookup"><span data-stu-id="14089-123">One person (or thread) can handle all these tasks.</span></span> <span data-ttu-id="14089-124">朝食の例を続けると、1 人で、最初の作業が完了する前に次の作業を開始して、非同期に朝食を作ることができます。</span><span class="sxs-lookup"><span data-stu-id="14089-124">Continuing the breakfast analogy, one person can make breakfast asynchronously by starting the next task before the first completes.</span></span> <span data-ttu-id="14089-125">調理はそれを監視している人がいるかどうかに関係なく進行します。</span><span class="sxs-lookup"><span data-stu-id="14089-125">The cooking progresses whether or not someone is watching it.</span></span> <span data-ttu-id="14089-126">卵用のフライパンを熱し始めたらすぐに、ベーコンを焼き始めることができます。</span><span class="sxs-lookup"><span data-stu-id="14089-126">As soon as you start warming the pan for the eggs, you can begin frying the bacon.</span></span> <span data-ttu-id="14089-127">ベーコンを焼き始めたら、パンをトースターに入れることができます。</span><span class="sxs-lookup"><span data-stu-id="14089-127">Once the bacon starts, you can put the bread into the toaster.</span></span>

<span data-ttu-id="14089-128">並列アルゴリズムの場合は、複数の料理人 (つまりスレッド) が必要です。</span><span class="sxs-lookup"><span data-stu-id="14089-128">For a parallel algorithm, you'd need multiple cooks (or threads).</span></span> <span data-ttu-id="14089-129">1 人は卵を焼き、1 人はベーコンを焼く、といった具合です。</span><span class="sxs-lookup"><span data-stu-id="14089-129">One would make the eggs, one the bacon, and so on.</span></span> <span data-ttu-id="14089-130">それぞれは、1 つのタスクだけに集中します。</span><span class="sxs-lookup"><span data-stu-id="14089-130">Each one would be focused on just that one task.</span></span> <span data-ttu-id="14089-131">各料理人 (つまりスレッド) は、ベーコンを裏返すことができるようになるまで、またはトーストが飛び出すまで待つ間は、同期的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14089-131">Each cook (or thread) would be blocked synchronously waiting for bacon to be ready to flip, or the toast to pop.</span></span>

<span data-ttu-id="14089-132">それでは、これと同じ命令が C# ステートメントとして書かれている場合を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="14089-132">Now, consider those same instructions written as C# statements:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-starter/Program.cs" highlight="8-27":::

:::image type="content" source="media/synchronous-breakfast.png" alt-text="同期的な朝食":::

<span data-ttu-id="14089-134">同期的に準備された朝食は、合計が個々のタスクの合計であるため、約 30 分かかりました。</span><span class="sxs-lookup"><span data-stu-id="14089-134">The synchronously prepared breakfast, took roughly 30 minutes because the total is the sum of each individual task.</span></span>

> [!NOTE]
> <span data-ttu-id="14089-135">`Coffee`、`Egg`、`Bacon`、`Toast`、および `Juice` クラスは空です。</span><span class="sxs-lookup"><span data-stu-id="14089-135">The `Coffee`, `Egg`, `Bacon`, `Toast`, and `Juice` classes are empty.</span></span> <span data-ttu-id="14089-136">これらは、デモンストレーション目的の単なるマーカー クラスであり、プロパティは含まれず、その他の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="14089-136">They are simply marker classes for the purpose of demonstration, contain no properties, and serve no other purpose.</span></span>

<span data-ttu-id="14089-137">コンピューターによって、人と同じように命令が解釈されることはありません。</span><span class="sxs-lookup"><span data-stu-id="14089-137">Computers don't interpret those instructions the same way people do.</span></span> <span data-ttu-id="14089-138">コンピューターでは、作業が完了するまで各ステートメントはブロックされ、完了すると次のステートメントに進みます。</span><span class="sxs-lookup"><span data-stu-id="14089-138">The computer will block on each statement until the work is complete before moving on to the next statement.</span></span> <span data-ttu-id="14089-139">それではおいしい朝食はできません。</span><span class="sxs-lookup"><span data-stu-id="14089-139">That creates an unsatisfying breakfast.</span></span> <span data-ttu-id="14089-140">後のタスクは、前のタスクが完了するまで開始されません。</span><span class="sxs-lookup"><span data-stu-id="14089-140">The later tasks wouldn't be started until the earlier tasks had completed.</span></span> <span data-ttu-id="14089-141">朝食の支度でこんなことをしていると、ずっと長い時間がかかり、提供される前に冷めてしまう料理もあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="14089-141">It would take much longer to create the breakfast, and some items would have gotten cold before being served.</span></span>

<span data-ttu-id="14089-142">上のような手順をコンピューターに非同期に実行させたい場合は、非同期のコードを書く必要があります。</span><span class="sxs-lookup"><span data-stu-id="14089-142">If you want the computer to execute the above instructions asynchronously, you must write asynchronous code.</span></span>

<span data-ttu-id="14089-143">今日書いているプログラムでは、このようなことを考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="14089-143">These concerns are important for the programs you write today.</span></span> <span data-ttu-id="14089-144">クライアント プログラムを書くときは、ユーザー入力に対する UI の応答性をよくする必要です。</span><span class="sxs-lookup"><span data-stu-id="14089-144">When you write client programs, you want the UI to be responsive to user input.</span></span> <span data-ttu-id="14089-145">Web からデータをダウンロードしている間、電話がフリーズしたようになるアプリケーションではいけません。</span><span class="sxs-lookup"><span data-stu-id="14089-145">Your application shouldn't make a phone appear frozen while it's downloading data from the web.</span></span> <span data-ttu-id="14089-146">サーバーのプログラムを書くときは、スレッドがブロックされては困ります。</span><span class="sxs-lookup"><span data-stu-id="14089-146">When you write server programs, you don't want threads blocked.</span></span> <span data-ttu-id="14089-147">それらのスレッドは、他の要求を処理しているかもしれません。</span><span class="sxs-lookup"><span data-stu-id="14089-147">Those threads could be serving other requests.</span></span> <span data-ttu-id="14089-148">非同期の代替手段が存在する場合に同期コードを使用すると、低コストでスケールアウトする能力が低下してしまいます。</span><span class="sxs-lookup"><span data-stu-id="14089-148">Using synchronous code when asynchronous alternatives exist hurts your ability to scale out less expensively.</span></span> <span data-ttu-id="14089-149">ブロックされたスレッドに料金を支払うことになります。</span><span class="sxs-lookup"><span data-stu-id="14089-149">You pay for those blocked threads.</span></span>

<span data-ttu-id="14089-150">よくできた最新のアプリケーションには、非同期コードが必要です。</span><span class="sxs-lookup"><span data-stu-id="14089-150">Successful modern applications require asynchronous code.</span></span> <span data-ttu-id="14089-151">言語のサポートがない場合、非同期コードを書くには、コールバック、完了イベント、またはコードの本来の意図をわかりにくくしてしまうような他の手段が必要でした。</span><span class="sxs-lookup"><span data-stu-id="14089-151">Without language support, writing asynchronous code required callbacks, completion events, or other means that obscured the original intent of the code.</span></span> <span data-ttu-id="14089-152">同期コードの利点は、段階的なアクションによりスキャンと理解が容易なことです。</span><span class="sxs-lookup"><span data-stu-id="14089-152">The advantage of the synchronous code is that it's step-by-step actions make it easy to scan and understand.</span></span> <span data-ttu-id="14089-153">従来の非同期モデルでは、開発者はコードの基本的な処理ではなく、コードの非同期的性質に注目することを余儀なくされました。</span><span class="sxs-lookup"><span data-stu-id="14089-153">Traditional asynchronous models forced you to focus on the asynchronous nature of the code, not on the fundamental actions of the code.</span></span>

## <a name="dont-block-await-instead"></a><span data-ttu-id="14089-154">ブロックするのではなく待機する</span><span class="sxs-lookup"><span data-stu-id="14089-154">Don't block, await instead</span></span>

<span data-ttu-id="14089-155">上記のコードは、非同期的な操作を実行するために同期的なコードを作成するという、不適切な手法の例です。</span><span class="sxs-lookup"><span data-stu-id="14089-155">The preceding code demonstrates a bad practice: constructing synchronous code to perform asynchronous operations.</span></span> <span data-ttu-id="14089-156">このようなコードを書くと、それを実行するスレッドは、他の作業を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="14089-156">As written, this code blocks the thread executing it from doing any other work.</span></span> <span data-ttu-id="14089-157">何らかのタスクの処理中は割り込まれません。</span><span class="sxs-lookup"><span data-stu-id="14089-157">It won't be interrupted while any of the tasks are in progress.</span></span> <span data-ttu-id="14089-158">パンを入れた後でトースターをじっと見詰めているようなものです。</span><span class="sxs-lookup"><span data-stu-id="14089-158">It would be as though you stared at the toaster after putting the bread in.</span></span> <span data-ttu-id="14089-159">トーストが飛び出すまで、誰かから話し掛けられても無視するでしょう。</span><span class="sxs-lookup"><span data-stu-id="14089-159">You'd ignore anyone talking to you until the toast popped.</span></span>

<span data-ttu-id="14089-160">タスクの実行中にスレッドをブロックしないように、このコードを更新することから始めましょう。</span><span class="sxs-lookup"><span data-stu-id="14089-160">Let's start by updating this code so that the thread doesn't block while tasks are running.</span></span> <span data-ttu-id="14089-161">`await` キーワードを使用すると、ブロックしない方法でタスクを開始し、タスクが完了したら実行を継続できます。</span><span class="sxs-lookup"><span data-stu-id="14089-161">The `await` keyword provides a non-blocking way to start a task, then continue execution when that task completes.</span></span> <span data-ttu-id="14089-162">朝食作成コードの簡単な非同期バージョンは、次のスニペットのようになります。</span><span class="sxs-lookup"><span data-stu-id="14089-162">A simple asynchronous version of the make a breakfast code would look like the following snippet:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V2/Program.cs" id="SnippetMain":::

> [!IMPORTANT]
> <span data-ttu-id="14089-163">合計経過時間は、初期の同期バージョンとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="14089-163">The total elapsed time is roughly the same as the initial synchonous version.</span></span> <span data-ttu-id="14089-164">このコードでは、非同期プログラミングの主要な機能のいくつかがまだ利用されています。</span><span class="sxs-lookup"><span data-stu-id="14089-164">The code has yet to take advantage of some of the key features of asynchronous programming.</span></span>

> [!TIP]
> <span data-ttu-id="14089-165">`FryEggsAsync`、`FryBaconAsync`、`ToastBreadAsync` のメソッド本体がすべて更新され、それぞれ `Task<Egg>`、`Task<Bacon>`、および `Task<Toast>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="14089-165">The method bodies of the `FryEggsAsync`, `FryBaconAsync`, and `ToastBreadAsync` have all been updated to return `Task<Egg>`, `Task<Bacon>`, and `Task<Toast>` respectively.</span></span> <span data-ttu-id="14089-166">メソッドは、元のバージョンから名前が変更され、"Async" サフィックスが含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="14089-166">The methods are renamed from their original version to include the "Async" suffix.</span></span> <span data-ttu-id="14089-167">これらの実装は、この記事で後述する[最終バージョン](#final-version)の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="14089-167">Their implementations are shown as part of the [final version](#final-version) later in this article.</span></span>

<span data-ttu-id="14089-168">このコードでは、卵またはベーコンを調理している間、ブロックすることはありません。</span><span class="sxs-lookup"><span data-stu-id="14089-168">This code doesn't block while the eggs or the bacon are cooking.</span></span> <span data-ttu-id="14089-169">ただし、このコードは他のタスクを開始しません。</span><span class="sxs-lookup"><span data-stu-id="14089-169">This code won't start any other tasks though.</span></span> <span data-ttu-id="14089-170">まだ、トースターにトーストを入れた後、トーストが飛び出すまで眺めています。</span><span class="sxs-lookup"><span data-stu-id="14089-170">You'd still put the toast in the toaster and stare at it until it pops.</span></span> <span data-ttu-id="14089-171">ただし、少なくとも誰かが注意を引こうとしたら反応するようにはなります。</span><span class="sxs-lookup"><span data-stu-id="14089-171">But at least, you'd respond to anyone that wanted your attention.</span></span> <span data-ttu-id="14089-172">複数の注文を受けるレストランでは、料理人は最初の朝食を作っている間に、別の朝食を作り始めます。</span><span class="sxs-lookup"><span data-stu-id="14089-172">In a restaurant where multiple orders are placed, the cook could start another breakfast while the first is cooking.</span></span>

<span data-ttu-id="14089-173">この場合、開始してまだ完了していないタスクを待っている間、朝食作業スレッドはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="14089-173">Now, the thread working on the breakfast isn't blocked while awaiting any started task that hasn't yet finished.</span></span> <span data-ttu-id="14089-174">一部のアプリケーションでは、必要な変更はこれですべてです。</span><span class="sxs-lookup"><span data-stu-id="14089-174">For some applications, this change is all that's needed.</span></span> <span data-ttu-id="14089-175">GUI アプリケーションは、この変更だけで引き続きユーザーに応答します。</span><span class="sxs-lookup"><span data-stu-id="14089-175">A GUI application still responds to the user with just this change.</span></span> <span data-ttu-id="14089-176">ただし、このシナリオでは、これだけでは十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="14089-176">However, for this scenario, you want more.</span></span> <span data-ttu-id="14089-177">各コンポーネントのタスクを順番に実行したくはありません。</span><span class="sxs-lookup"><span data-stu-id="14089-177">You don't want each of the component tasks to be executed sequentially.</span></span> <span data-ttu-id="14089-178">前のタスクの完了を待機する前に、各コンポーネントのタスクを開始した方がよさそうです。</span><span class="sxs-lookup"><span data-stu-id="14089-178">It's better to start each of the component tasks before awaiting the previous task's completion.</span></span>

## <a name="start-tasks-concurrently"></a><span data-ttu-id="14089-179">タスクを同時に開始する</span><span class="sxs-lookup"><span data-stu-id="14089-179">Start tasks concurrently</span></span>

<span data-ttu-id="14089-180">多くのシナリオでは、複数の独立したタスクをすぐに開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14089-180">In many scenarios, you want to start several independent tasks immediately.</span></span> <span data-ttu-id="14089-181">そうすれば、各タスクが完了したら、準備のできている他のタスクを続行できます。</span><span class="sxs-lookup"><span data-stu-id="14089-181">Then, as each task finishes, you can continue other work that's ready.</span></span> <span data-ttu-id="14089-182">朝食でたとえるなら、もっと早く朝食を準備できます。</span><span class="sxs-lookup"><span data-stu-id="14089-182">In the breakfast analogy, that's how you get breakfast done more quickly.</span></span> <span data-ttu-id="14089-183">また、すべての作業がほぼ同じタイミングで終了します。</span><span class="sxs-lookup"><span data-stu-id="14089-183">You also get everything done close to the same time.</span></span> <span data-ttu-id="14089-184">できたての朝食を食べられます。</span><span class="sxs-lookup"><span data-stu-id="14089-184">You'll get a hot breakfast.</span></span>

<span data-ttu-id="14089-185"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> および関連する型を使用して、進行中のタスクについて判断できます。</span><span class="sxs-lookup"><span data-stu-id="14089-185">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> and related types are classes you can use to reason about tasks that are in progress.</span></span> <span data-ttu-id="14089-186">それを使用すると、実際の朝食作成方法にさらに近いコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="14089-186">That enables you to write code that more closely resembles the way you'd actually create breakfast.</span></span> <span data-ttu-id="14089-187">卵、ベーコン、トーストの調理を同時に始めます。</span><span class="sxs-lookup"><span data-stu-id="14089-187">You'd start cooking the eggs, bacon, and toast at the same time.</span></span> <span data-ttu-id="14089-188">それぞれでアクションが必要になったら、そのタスクに注意を向け、次のアクションを行ってから、注意が必要な他のタスクを待ちます。</span><span class="sxs-lookup"><span data-stu-id="14089-188">As each requires action, you'd turn your attention to that task, take care of the next action, then await for something else that requires your attention.</span></span>

<span data-ttu-id="14089-189">タスクを開始し、作業を表す <xref:System.Threading.Tasks.Task> オブジェクトを保持します。</span><span class="sxs-lookup"><span data-stu-id="14089-189">You start a task and hold on to the <xref:System.Threading.Tasks.Task> object that represents the work.</span></span> <span data-ttu-id="14089-190">各タスクを `await` (待機) してから、結果を処理します。</span><span class="sxs-lookup"><span data-stu-id="14089-190">You'll `await` each task before working with its result.</span></span>

<span data-ttu-id="14089-191">朝食コードに対してこれらの変更を行いましょう。</span><span class="sxs-lookup"><span data-stu-id="14089-191">Let's make these changes to the breakfast code.</span></span> <span data-ttu-id="14089-192">最初のステップは、操作のタスクを開始するときに、それらを待機するのではなく、保存することです。</span><span class="sxs-lookup"><span data-stu-id="14089-192">The first step is to store the tasks for operations when they start, rather than awaiting them:</span></span>

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");

Task<Bacon> baconTask = FryBaconAsync(3);
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Task<Toast> toastTask = ToastBreadAsync(2);
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");

Juice oj = PourOJ();
Console.WriteLine("oj is ready");
Console.WriteLine("Breakfast is ready!");
```

<span data-ttu-id="14089-193">次に、ベーコンと卵の `await` ステートメントを、メソッドの最後の朝食提供前に移動します。</span><span class="sxs-lookup"><span data-stu-id="14089-193">Next, you can move the `await` statements for the bacon and eggs to the end of the method, before serving breakfast:</span></span>

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Task<Bacon> baconTask = FryBaconAsync(3);
Task<Toast> toastTask = ToastBreadAsync(2);

Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");
Juice oj = PourOJ();
Console.WriteLine("oj is ready");

Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Console.WriteLine("Breakfast is ready!");
```

:::image type="content" source="media/asynchronous-breakfast.png" alt-text="非同期的な朝食":::

<span data-ttu-id="14089-195">非同期的に準備された朝食は、約 20 分かかりました。これは、いくつかのタスクを同時に実行できたことが理由です。</span><span class="sxs-lookup"><span data-stu-id="14089-195">The asynchronously prepared breakfast took roughly 20 minutes, this is because some tasks were able to run concurrently.</span></span>

<span data-ttu-id="14089-196">上のコードの方がより適切に動作します。</span><span class="sxs-lookup"><span data-stu-id="14089-196">The preceding code works better.</span></span> <span data-ttu-id="14089-197">すべての非同期タスクを一度に開始します。</span><span class="sxs-lookup"><span data-stu-id="14089-197">You start all the asynchronous tasks at once.</span></span> <span data-ttu-id="14089-198">結果が必要なときにのみ、各タスクを待機します。</span><span class="sxs-lookup"><span data-stu-id="14089-198">You await each task only when you need the results.</span></span> <span data-ttu-id="14089-199">上記のコードは、異なるマイクロサービスに要求を行って 1 つのページに結果をまとめる Web アプリケーションのコードに似ているかもしれません。</span><span class="sxs-lookup"><span data-stu-id="14089-199">The preceding code may be similar to code in a web application that makes requests of different microservices, then combines the results into a single page.</span></span> <span data-ttu-id="14089-200">すべての要求をすぐに行った後、すべてのタスクを `await` して、Web ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="14089-200">You'll make all the requests immediately, then `await` all those tasks and compose the web page.</span></span>

## <a name="composition-with-tasks"></a><span data-ttu-id="14089-201">タスクの合成</span><span class="sxs-lookup"><span data-stu-id="14089-201">Composition with tasks</span></span>

 <span data-ttu-id="14089-202">トーストを除き、朝食のすべての準備が同時に整います。</span><span class="sxs-lookup"><span data-stu-id="14089-202">You have everything ready for breakfast at the same time except the toast.</span></span> <span data-ttu-id="14089-203">トーストの作成は、非同期操作 (パンを焼く) と同期操作 (バターとジャムを塗る) の合成です。</span><span class="sxs-lookup"><span data-stu-id="14089-203">Making the toast is the composition of an asynchronous operation (toasting the bread), and synchronous operations (adding the butter and the jam).</span></span> <span data-ttu-id="14089-204">このコードの更新では、重要な概念が示されています。</span><span class="sxs-lookup"><span data-stu-id="14089-204">Updating this code illustrates an important concept:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14089-205">非同期操作とその後の同期操作の合成は、非同期操作です。</span><span class="sxs-lookup"><span data-stu-id="14089-205">The composition of an asynchronous operation followed by synchronous work is an asynchronous operation.</span></span> <span data-ttu-id="14089-206">言い方を変えれば、操作の一部が非同期である場合、操作全体が非同期になります。</span><span class="sxs-lookup"><span data-stu-id="14089-206">Stated another way, if any portion of an operation is asynchronous, the entire operation is asynchronous.</span></span>

<span data-ttu-id="14089-207">上記のコードでは、<xref:System.Threading.Tasks.Task> または <xref:System.Threading.Tasks.Task%601> オブジェクトを使用して実行中のタスクを保持できることを示しました。</span><span class="sxs-lookup"><span data-stu-id="14089-207">The preceding code showed you that you can use <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> objects to hold running tasks.</span></span> <span data-ttu-id="14089-208">結果を使用する前に、各タスクを `await` します。</span><span class="sxs-lookup"><span data-stu-id="14089-208">You `await` each task before using its result.</span></span> <span data-ttu-id="14089-209">次のステップは、他の作業の組み合わせを表すメソッドを作成することです。</span><span class="sxs-lookup"><span data-stu-id="14089-209">The next step is to create methods that represent the combination of other work.</span></span> <span data-ttu-id="14089-210">朝食を提供するには、バターとジャムを塗る前にパンを焼くタスクを待機します。</span><span class="sxs-lookup"><span data-stu-id="14089-210">Before serving breakfast, you want to await the task that represents toasting the bread before adding butter and jam.</span></span> <span data-ttu-id="14089-211">次のコードでその作業を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="14089-211">You can represent that work with the following code:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" id="SnippetComposeToastTask":::

<span data-ttu-id="14089-212">上のメソッドのシグニチャには `async` 修飾子が付いています。</span><span class="sxs-lookup"><span data-stu-id="14089-212">The preceding method has the `async` modifier in its signature.</span></span> <span data-ttu-id="14089-213">それにより、コンパイラに対して、このメソッドに `await` ステートメントが含まれることが通知されます。それには非同期操作が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14089-213">That signals to the compiler that this method contains an `await` statement; it contains asynchronous operations.</span></span> <span data-ttu-id="14089-214">このメソッドは、パンを焼いてからバターとジャムを塗るタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="14089-214">This method represents the task that toasts the bread, then adds butter and jam.</span></span> <span data-ttu-id="14089-215">このメソッドからは、これら 3 つの操作の合成を表す <xref:System.Threading.Tasks.Task%601> が返されます。</span><span class="sxs-lookup"><span data-stu-id="14089-215">This method returns a <xref:System.Threading.Tasks.Task%601> that represents the composition of those three operations.</span></span> <span data-ttu-id="14089-216">これで、コードのメイン ブロックは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="14089-216">The main block of code now becomes:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" id="SnippetMain":::

<span data-ttu-id="14089-217">この変更では、非同期コードを使用するための重要な手法が示されています。</span><span class="sxs-lookup"><span data-stu-id="14089-217">The previous change illustrated an important technique for working with asynchronous code.</span></span> <span data-ttu-id="14089-218">タスクを返す新しいメソッドに操作を分離することで、タスクを合成します。</span><span class="sxs-lookup"><span data-stu-id="14089-218">You compose tasks by separating the operations into a new method that returns a task.</span></span> <span data-ttu-id="14089-219">そのタスクを待機するタイミングを選択できます。</span><span class="sxs-lookup"><span data-stu-id="14089-219">You can choose when to await that task.</span></span> <span data-ttu-id="14089-220">他のタスクを同時に開始できます。</span><span class="sxs-lookup"><span data-stu-id="14089-220">You can start other tasks concurrently.</span></span>

## <a name="await-tasks-efficiently"></a><span data-ttu-id="14089-221">タスクを効率的に待機する</span><span class="sxs-lookup"><span data-stu-id="14089-221">Await tasks efficiently</span></span>

<span data-ttu-id="14089-222">上記のコードの最後にある一連の `await` ステートメントは、`Task` クラスのメソッドを使用することによって改良できます。</span><span class="sxs-lookup"><span data-stu-id="14089-222">The series of `await` statements at the end of the preceding code can be improved by using methods of the `Task` class.</span></span> <span data-ttu-id="14089-223">それらの API の 1 つは <xref:System.Threading.Tasks.Task.WhenAll%2A> であり、これにより次のコードで示すように、引数リストのすべてのタスクが完了すると完了する <xref:System.Threading.Tasks.Task> が返されます。</span><span class="sxs-lookup"><span data-stu-id="14089-223">One of those APIs is <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns a <xref:System.Threading.Tasks.Task> that completes when all the tasks in its argument list have completed, as shown in the following code:</span></span>

```csharp
await Task.WhenAll(eggsTask, baconTask, toastTask);
Console.WriteLine("eggs are ready");
Console.WriteLine("bacon is ready");
Console.WriteLine("toast is ready");
Console.WriteLine("Breakfast is ready!");
```

<span data-ttu-id="14089-224">もう 1 つのオプションは、<xref:System.Threading.Tasks.Task.WhenAny%2A> を使用することです。これは、引数のいずれかが完了すると完了する `Task<Task>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="14089-224">Another option is to use <xref:System.Threading.Tasks.Task.WhenAny%2A>, which returns a `Task<Task>` that completes when any of its arguments completes.</span></span> <span data-ttu-id="14089-225">返されたタスクを待機して、既に完了したことを把握できます。</span><span class="sxs-lookup"><span data-stu-id="14089-225">You can await the returned task, knowing that it has already finished.</span></span> <span data-ttu-id="14089-226">次のコードでは、<xref:System.Threading.Tasks.Task.WhenAny%2A> を使用して最初のタスクが完了するのを待った後、その結果を処理する方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="14089-226">The following code shows how you could use <xref:System.Threading.Tasks.Task.WhenAny%2A> to await the first task to finish and then process its result.</span></span> <span data-ttu-id="14089-227">完了したタスクの結果を処理した後、`WhenAny` に渡すタスクの一覧からその完了したタスクを削除します。</span><span class="sxs-lookup"><span data-stu-id="14089-227">After processing the result from the completed task, you remove that completed task from the list of tasks passed to `WhenAny`.</span></span>

```csharp
var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("toast is ready");
    }
    breakfastTasks.Remove(finishedTask);
}
```

<span data-ttu-id="14089-228">すべてを変更した後、コードの最終バージョンは <a id="final-version"></a> のようになります。</span><span class="sxs-lookup"><span data-stu-id="14089-228">After all those changes, the final version of the code looks like this: <a id="final-version"></a></span></span>
:::code language="csharp" source="snippets/index/AsyncBreakfast-final/Program.cs" highlight="9-40":::

:::image type="content" source="media/whenany-async-breakfast.png" alt-text="非同期的な朝食がある場合":::

<span data-ttu-id="14089-230">非同期に準備された朝食の最終バージョンは、約 15 分かかりました。これは、いくつかのタスクを同時に実行でき、コードで一度に複数のタスクを監視して必要なときにのみアクションを実行できるようになったためです。</span><span class="sxs-lookup"><span data-stu-id="14089-230">The final version of the asynchronously prepared breakfast took roughly 15 minutes, this is because some tasks were able to run concurrently, and the code was able to monitor multiple tasks at once and only take action when it was needed.</span></span>

<span data-ttu-id="14089-231">この最後のコードは非同期です。</span><span class="sxs-lookup"><span data-stu-id="14089-231">This final code is asynchronous.</span></span> <span data-ttu-id="14089-232">人が朝食を作る方法が、より正確に反映されています。</span><span class="sxs-lookup"><span data-stu-id="14089-232">It more accurately reflects how a person would cook a breakfast.</span></span> <span data-ttu-id="14089-233">上のコードを、この記事の最初のコード サンプルと比較してください。</span><span class="sxs-lookup"><span data-stu-id="14089-233">Compare the preceding code with the first code sample in this article.</span></span> <span data-ttu-id="14089-234">中核となるアクションはコードを読むと明らかです。</span><span class="sxs-lookup"><span data-stu-id="14089-234">The core actions are still clear from reading the code.</span></span> <span data-ttu-id="14089-235">このコードは、この記事の最初にある朝食の作成手順と同じように読むことができます。</span><span class="sxs-lookup"><span data-stu-id="14089-235">You can read this code the same way you'd read those instructions for making a breakfast at the beginning of this article.</span></span> <span data-ttu-id="14089-236">`async` および `await` の言語機能により、手順書に従うためにすべての人が行う変換が提供されます。つまり、可能になったらタスクを開始し、タスク完了の待機をブロックしないようにします。</span><span class="sxs-lookup"><span data-stu-id="14089-236">The language features for `async` and `await` provide the translation every person makes to follow those written instructions: start tasks as you can and don't block waiting for tasks to complete.</span></span>

## <a name="next-steps"></a><span data-ttu-id="14089-237">次の手順</span><span class="sxs-lookup"><span data-stu-id="14089-237">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14089-238">タスク非同期プログラミング モデルについて</span><span class="sxs-lookup"><span data-stu-id="14089-238">Learn about the task asynchronous programming model</span></span>](task-asynchronous-programming-model.md)
