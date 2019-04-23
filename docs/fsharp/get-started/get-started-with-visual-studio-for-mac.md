---
title: Mac 用 Visual Studio での F# の概要します。
description: 使用する方法について説明しますF#で Visual Studio for mac。
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331872"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="865da-103">Mac 用 Visual Studio での F# の概要します。</span><span class="sxs-lookup"><span data-stu-id="865da-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="865da-104">F# および Visual F# ツールは、for Mac IDE、Visual Studio でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="865da-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="865da-105">いる[Visual Studio for Mac がインストールされている](install-fsharp.md#install-f-with-visual-studio-for-mac)します。</span><span class="sxs-lookup"><span data-stu-id="865da-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="865da-106">コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="865da-106">Creating a console application</span></span>

<span data-ttu-id="865da-107">Visual Studio for Mac で最も基本的なプロジェクトの 1 つは、コンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="865da-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="865da-108">これを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="865da-108">Here's how to do it.</span></span>  <span data-ttu-id="865da-109">Visual Studio for Mac が起動したら。</span><span class="sxs-lookup"><span data-stu-id="865da-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="865da-110">**ファイル**メニューで、**新しいソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="865da-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="865da-111">新しいプロジェクト ダイアログ ボックスで、コンソール アプリケーションの 2 つの異なるテンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="865da-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="865da-112">その他の 1 つである .NET、.NET Framework を対象にする-> です。</span><span class="sxs-lookup"><span data-stu-id="865da-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="865da-113">他のテンプレートは、.NET Core では .NET Core を対象とするアプリ]-> [です。</span><span class="sxs-lookup"><span data-stu-id="865da-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="865da-114">この記事では、テンプレートのいずれかが動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="865da-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="865da-115">コンソール アプリを変更 (C#) F# に必要な場合。</span><span class="sxs-lookup"><span data-stu-id="865da-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="865da-116">選択、**次**前方に移動するボタン。</span><span class="sxs-lookup"><span data-stu-id="865da-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="865da-117">プロジェクトの名前を入力し、アプリで必要なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="865da-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="865da-118">選択したオプションに基づいて作成されるディレクトリ構造を表示する画面の端にあるプレビュー ウィンドウの通知。</span><span class="sxs-lookup"><span data-stu-id="865da-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="865da-119">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="865da-119">Click **Create**.</span></span>  <span data-ttu-id="865da-120">ソリューション エクスプ ローラーで F# プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="865da-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="865da-121">コードの記述</span><span class="sxs-lookup"><span data-stu-id="865da-121">Writing your code</span></span>

<span data-ttu-id="865da-122">最初にいくつかのコードを記述することで開始しましょう。</span><span class="sxs-lookup"><span data-stu-id="865da-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="865da-123">必ず、`Program.fs`ファイルを開くとを次の内容を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="865da-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="865da-124">上記のコード サンプルは、関数で`square`という名前の入力を受け取るが定義されている`x`単独で乗算します。</span><span class="sxs-lookup"><span data-stu-id="865da-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="865da-125">F#使用[型の推定](../language-reference/type-inference.md)の型`x`を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="865da-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="865da-126">F#コンパイラを選択し、乗算が有効な場合は、型を認識する型が割り当てられます`x`方法に基づいて`square`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="865da-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="865da-127">ポインターを合わせる場合`square`次を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="865da-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="865da-128">これは、関数の型のシグネチャと呼ばれるものです。</span><span class="sxs-lookup"><span data-stu-id="865da-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="865da-129">次のように読み取ることができます。"正方形をという名前の整数を受け取る関数は、x と整数が生成されます"。</span><span class="sxs-lookup"><span data-stu-id="865da-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="865da-130">コンパイラが付けた注`square`、`int`型今のところ、これは、乗算の間でジェネリックがないためには*すべて*型の場合ではなくジェネリック型の間では、します。</span><span class="sxs-lookup"><span data-stu-id="865da-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="865da-131">選択、F# コンパイラ`int`このポイントが調整されます型シグネチャを呼び出す場合`square`入力の種類などを変える、`float`します。</span><span class="sxs-lookup"><span data-stu-id="865da-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="865da-132">別の関数`main`が定義されているで装飾するが、 `EntryPoint` F# コンパイラにそのプログラムの実行を指示する属性を開始する必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="865da-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="865da-133">その他の場合と同じ規則に従って[C スタイルのプログラミング言語](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)コマンドライン引数は、この関数に渡すことができます、整数コードが返されます (通常`0`)。</span><span class="sxs-lookup"><span data-stu-id="865da-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="865da-134">このために呼び出される関数では、`square`関数の引数を持つ`12`します。</span><span class="sxs-lookup"><span data-stu-id="865da-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="865da-135">F#コンパイラの型が割り当てられます`square`する`int -> int`(を受け取る関数は、`int`を生成し、 `int`)。</span><span class="sxs-lookup"><span data-stu-id="865da-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="865da-136">呼び出し`printfn`を C スタイル プログラミング言語で、書式指定文字列で指定されている対応するパラメーターのような形式の文字列を使用して書式設定された印刷機能は、結果と、新しい行を出力します。</span><span class="sxs-lookup"><span data-stu-id="865da-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="865da-137">コードの実行</span><span class="sxs-lookup"><span data-stu-id="865da-137">Running your code</span></span>

<span data-ttu-id="865da-138">コードを実行し をクリックして結果を表示することができます**実行**トップ レベル メニューからし**デバッグなしで開始**します。</span><span class="sxs-lookup"><span data-stu-id="865da-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="865da-139">これは、デバッグを行わず、プログラムを実行し、結果を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="865da-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="865da-140">次の Visual Studio for Mac のポップアップをコンソール ウィンドウに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="865da-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="865da-141">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="865da-141">Congratulations!</span></span>  <span data-ttu-id="865da-142">Mac 用の Visual Studio で初めての F# プロジェクトを作成、F# の関数は、この関数の呼び出しの結果を印刷を記述してプロジェクトを実行し、いくつかの結果を参照してください。</span><span class="sxs-lookup"><span data-stu-id="865da-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="865da-143">使用してF#対話型</span><span class="sxs-lookup"><span data-stu-id="865da-143">Using F# Interactive</span></span>

<span data-ttu-id="865da-144">F# 対話型ウィンドウは、最適な機能では、Visual F# の Visual Studio for Mac ツールの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="865da-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="865da-145">経由で、そのコードを呼び出すし、対話形式で結果を参照してください、プロセスにコードを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="865da-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="865da-146">これを使用するには、強調表示、`square`コードで定義された関数。</span><span class="sxs-lookup"><span data-stu-id="865da-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="865da-147">次に、をクリックして**編集**トップ レベル メニューから。</span><span class="sxs-lookup"><span data-stu-id="865da-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="865da-148">次に選択**選択範囲を F# Interactive に送信**します。</span><span class="sxs-lookup"><span data-stu-id="865da-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="865da-149">これには、F# 対話型ウィンドウで、コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="865da-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="865da-150">または、選択範囲を右クリックし、選択**選択範囲を F# Interactive に送信**します。</span><span class="sxs-lookup"><span data-stu-id="865da-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="865da-151">表示する必要があります、F#対話型ウィンドウは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="865da-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="865da-152">同じ関数のシグネチャが表示されます、`square`関数で、関数の上にカーソルを配置するときに表示します。</span><span class="sxs-lookup"><span data-stu-id="865da-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="865da-153">`square`が F# Interactive プロセスで定義されている、ここではさまざまな値を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="865da-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="865da-154">関数を実行します。 これには、新しい名前に、結果をバインド`it`、種類と値の表示と`it`します。</span><span class="sxs-lookup"><span data-stu-id="865da-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="865da-155">各行を終了する必要がありますに注意してください。`;;`します。</span><span class="sxs-lookup"><span data-stu-id="865da-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="865da-156">これは、どのように F# Interactive を知っている、関数呼び出しが完了するとします。</span><span class="sxs-lookup"><span data-stu-id="865da-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="865da-157">新しい関数を定義することもできますF#Interactive:。</span><span class="sxs-lookup"><span data-stu-id="865da-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="865da-158">上の定義を新しい関数の場合、 `isOdd`、受け取り、`int`と奇数かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="865da-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="865da-159">異なる入力で返される内容を表示するには、この関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="865da-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="865da-160">関数呼び出し内の関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="865da-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="865da-161">使用することも、 [- 前方パイプ演算子](../language-reference/symbol-and-operator-reference/index.md)に 2 つの関数に値を渡すパイプラインします。</span><span class="sxs-lookup"><span data-stu-id="865da-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="865da-162">以降のチュートリアルでは、順方向のパイプ演算子などがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="865da-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="865da-163">ここでは、F# Interactive で何ができるかを大まかに取り上げているだけです。</span><span class="sxs-lookup"><span data-stu-id="865da-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="865da-164">詳細については、[F# を使用した対話型プログラミング](../tutorials/fsharp-interactive/index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="865da-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="865da-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="865da-165">Next steps</span></span>

<span data-ttu-id="865da-166">まだインストールしていない場合はチェック アウト、 [F# のツアー](../tour.md)、F# 言語のコア機能の一部が含まれています。</span><span class="sxs-lookup"><span data-stu-id="865da-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="865da-167">一部の F# の機能の概要が表示され Visual Studio for Mac にコピーして実行できる十分なコード サンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="865da-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="865da-168">使用できますが、いくつかの優れた外部リソースがあるの紹介、 [F# ガイド](../index.md)します。</span><span class="sxs-lookup"><span data-stu-id="865da-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="865da-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="865da-169">See also</span></span>

- [<span data-ttu-id="865da-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="865da-170">Visual F#</span></span>](../index.md)
- [<span data-ttu-id="865da-171">F# のツアー</span><span class="sxs-lookup"><span data-stu-id="865da-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="865da-172">F#言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="865da-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="865da-173">型の推論</span><span class="sxs-lookup"><span data-stu-id="865da-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="865da-174">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="865da-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
