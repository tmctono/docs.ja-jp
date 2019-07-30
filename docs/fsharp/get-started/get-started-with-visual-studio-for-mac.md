---
title: Mac 用 Visual Studio での F# の概要します。
description: を Visual Studio for Mac と共F#に使用する方法について説明します。
ms.date: 07/03/2018
ms.openlocfilehash: 679ed1ea28f5d0e0d910dbd407b38d1d2f0314f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629757"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="0bc0a-103">Mac 用 Visual Studio での F# の概要します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="0bc0a-104">F# および Visual F# ツールは、for Mac IDE、Visual Studio でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="0bc0a-105">[Visual Studio for Mac がインストールされ](install-fsharp.md#install-f-with-visual-studio-for-mac)ていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="0bc0a-106">コンソールアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="0bc0a-106">Creating a console application</span></span>

<span data-ttu-id="0bc0a-107">Visual Studio for Mac の最も基本的なプロジェクトの1つは、コンソールアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="0bc0a-108">これを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-108">Here's how to do it.</span></span>  <span data-ttu-id="0bc0a-109">Visual Studio for Mac が開いたら、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="0bc0a-110">**[ファイル]** メニューの **[新しいソリューション]** をポイントします。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="0bc0a-111">[新しいプロジェクト] ダイアログには、コンソールアプリケーションに2つの異なるテンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="0bc0a-112">.NET Framework をターゲットとする > .NET の下に1つあります。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="0bc0a-113">その他のテンプレートは .net core > アプリの下にあり、.NET Core を対象としています。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="0bc0a-114">どちらのテンプレートも、この記事の目的で機能します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="0bc0a-115">コンソール アプリを変更 (C#) F# に必要な場合。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="0bc0a-116">**[次へ]** ボタンをクリックして先に進みます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="0bc0a-117">プロジェクトに名前を付け、アプリに必要なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="0bc0a-118">プレビューウィンドウには、選択したオプションに基づいて作成されるディレクトリ構造が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="0bc0a-119">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-119">Click **Create**.</span></span>  <span data-ttu-id="0bc0a-120">ソリューション エクスプ ローラーで F# プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="0bc0a-121">コードの記述</span><span class="sxs-lookup"><span data-stu-id="0bc0a-121">Writing your code</span></span>

<span data-ttu-id="0bc0a-122">まず、コードをいくつか記述してみましょう。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="0bc0a-123">`Program.fs`ファイルが開いていることを確認し、その内容を次の内容に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="0bc0a-124">前のコードサンプルでは、と`square`いう名前`x`の入力を受け取り、それを単独で乗算する関数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="0bc0a-125">でF#は[型の推定](../language-reference/type-inference.md)が使用さ`x`れるため、の型を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="0bc0a-126">コンパイラF#は、乗算が有効な型を認識し、が呼び出される方法`x` `square`に基づいて型をに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="0bc0a-127">マウスポインター `square`を合わせると、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="0bc0a-128">これは、関数の型シグネチャとして知られています。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="0bc0a-129">次のように読み取ることができます。"Square は、x という整数を受け取り、整数を生成する関数です。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="0bc0a-130">コンパイラ`square`によって型が`int`設定されていることに注意してください。これは、乗算が*すべて*の型のジェネリックではなく、閉じられた型のセット全体でジェネリックであるためです。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="0bc0a-131">選択、F# コンパイラ`int`このポイントが調整されます型シグネチャを呼び出す場合`square`入力の種類などを変える、`float`します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="0bc0a-132">別の関数`main`が定義されているで装飾するが、 `EntryPoint` F# コンパイラにそのプログラムの実行を指示する属性を開始する必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="0bc0a-133">これは、コマンドライン引数をこの関数に渡すことができる他の[C スタイルのプログラミング言語](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)と同じ規則に従い、整数のコードが返され`0`ます (通常は)。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="0bc0a-134">この関数は、 `square` `12`引数を指定して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="0bc0a-135">コンパイラF#は、の`square`型をに`int -> int`割り当てます。これ`int`は、を受け取り、を生成`int`する関数です。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="0bc0a-136">の呼び出し`printfn`は、書式指定文字列を使用する書式設定された印刷関数で、C スタイルのプログラミング言語に似ています。また、書式指定文字列で指定されたパラメーターに対応するパラメーターを使用して、結果と改行を出力します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="0bc0a-137">コードの実行</span><span class="sxs-lookup"><span data-stu-id="0bc0a-137">Running your code</span></span>

<span data-ttu-id="0bc0a-138">上部のメニューから **[実行]** をクリックし、 **[デバッグなしで開始]** をクリックして、コードを実行し、結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="0bc0a-139">これにより、デバッグなしでプログラムが実行され、結果を確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="0bc0a-140">コンソールウィンドウに次の出力が表示され、Visual Studio for Mac ポップアップされます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="0bc0a-141">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="0bc0a-141">Congratulations!</span></span>  <span data-ttu-id="0bc0a-142">Mac 用の Visual Studio で初めての F# プロジェクトを作成、F# の関数は、この関数の呼び出しの結果を印刷を記述してプロジェクトを実行し、いくつかの結果を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="0bc0a-143">対話型F#の使用</span><span class="sxs-lookup"><span data-stu-id="0bc0a-143">Using F# Interactive</span></span>

<span data-ttu-id="0bc0a-144">F# 対話型ウィンドウは、最適な機能では、Visual F# の Visual Studio for Mac ツールの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="0bc0a-145">このメソッドを使用すると、コードを呼び出して結果を対話形式で確認できるプロセスにコードを送信できます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="0bc0a-146">使用を開始するには、 `square`コードで定義されている関数を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="0bc0a-147">次に、トップレベルメニューの **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="0bc0a-148">次に選択**選択範囲を F# Interactive に送信**します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="0bc0a-149">これには、F# 対話型ウィンドウで、コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="0bc0a-150">または、選択範囲を右クリックし、選択**選択範囲を F# Interactive に送信**します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="0bc0a-151">F#対話型ウィンドウが表示され、次のようなウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="0bc0a-152">これは、関数をポイントした`square`ときに前に見た関数の関数シグネチャと同じです。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="0bc0a-153">`square`が F# Interactive プロセスで定義されている、ここではさまざまな値を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="0bc0a-154">これにより、関数が実行され、結果が`it`新しい名前にバインドされ、の`it`型と値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="0bc0a-155">各行は、で`;;`終了する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="0bc0a-156">これは、どのように F# Interactive を知っている、関数呼び出しが完了するとします。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="0bc0a-157">対話型でF#新しい関数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="0bc0a-158">上のでは新しい関数`isOdd`が定義されています。これはを`int`受け取り、それが奇数かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="0bc0a-159">この関数を呼び出すと、異なる入力で何が返されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="0bc0a-160">関数呼び出しの中で関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="0bc0a-161">[パイプ転送演算子](../language-reference/symbol-and-operator-reference/index.md)を使用して、値を次の2つの関数にパイプライン処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="0bc0a-162">パイプ転送演算子などの詳細については、以降のチュートリアルで説明します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="0bc0a-163">ここでは、F# Interactive で何ができるかを大まかに取り上げているだけです。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="0bc0a-164">詳細については、[F# を使用した対話型プログラミング](../tutorials/fsharp-interactive/index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0bc0a-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="0bc0a-165">Next steps</span></span>

<span data-ttu-id="0bc0a-166">まだインストールしていない場合はチェック アウト、 [F# のツアー](../tour.md)、F# 言語のコア機能の一部が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="0bc0a-167">一部の F# の機能の概要が表示され Visual Studio for Mac にコピーして実行できる十分なコード サンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="0bc0a-168">使用できますが、いくつかの優れた外部リソースがあるの紹介、 [F# ガイド](../index.md)します。</span><span class="sxs-lookup"><span data-stu-id="0bc0a-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0bc0a-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bc0a-169">See also</span></span>

- [<span data-ttu-id="0bc0a-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="0bc0a-170">Visual F#</span></span>](../index.md)
- [<span data-ttu-id="0bc0a-171">F# のツアー</span><span class="sxs-lookup"><span data-stu-id="0bc0a-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="0bc0a-172">F#言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="0bc0a-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="0bc0a-173">型の推論</span><span class="sxs-lookup"><span data-stu-id="0bc0a-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="0bc0a-174">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="0bc0a-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
