---
title: Visual Studio での F# の概要します。
description: Visual Studio で F# を使用する方法について説明します。
ms.date: 07/03/2018
ms.openlocfilehash: 9b02a5d295f982b1911dab567213fa9a2b6c4304
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754867"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="e7435-103">Visual Studio での F# の概要します。</span><span class="sxs-lookup"><span data-stu-id="e7435-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="e7435-104">F# および Visual F# ツールは、Visual Studio IDE でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e7435-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="e7435-105">作業を開始できることを確認します。 [Visual Studio をインストール F#](install-fsharp.md#install-f-with-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="e7435-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="e7435-106">コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7435-106">Creating a console application</span></span>

<span data-ttu-id="e7435-107">Visual Studio で最も基本的なプロジェクトの 1 つは、コンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e7435-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="e7435-108">これを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7435-108">Here's how to do it.</span></span>  <span data-ttu-id="e7435-109">Visual Studio が開くです。</span><span class="sxs-lookup"><span data-stu-id="e7435-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="e7435-110">**ファイル**メニューで、**新規**を選び、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="e7435-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="e7435-111">[プロジェクト] ダイアログで、新規で**テンプレート**、はず**Visual F#** します。</span><span class="sxs-lookup"><span data-stu-id="e7435-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="e7435-112">選択すると、表示、F#テンプレート。</span><span class="sxs-lookup"><span data-stu-id="e7435-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="e7435-113">いずれかを選択 **.NET Core コンソール アプリ**または**コンソール アプリ**します。</span><span class="sxs-lookup"><span data-stu-id="e7435-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="e7435-114">選択、**わかりました**F# プロジェクトを作成するボタン。</span><span class="sxs-lookup"><span data-stu-id="e7435-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="e7435-115">ソリューション エクスプ ローラーで F# プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7435-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="e7435-116">コードの記述</span><span class="sxs-lookup"><span data-stu-id="e7435-116">Writing your code</span></span>

<span data-ttu-id="e7435-117">最初にいくつかのコードを記述することで開始しましょう。</span><span class="sxs-lookup"><span data-stu-id="e7435-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="e7435-118">必ず、`Program.fs`ファイルを開くとを次の内容を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e7435-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="e7435-119">上記のコード サンプルは、関数で`square`という名前の入力を受け取るが定義されている`x`単独で乗算します。</span><span class="sxs-lookup"><span data-stu-id="e7435-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="e7435-120">F#使用[型の推定](../language-reference/type-inference.md)の型`x`を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7435-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="e7435-121">F#コンパイラを選択し、乗算が有効な場合は、型を認識する型が割り当てられます`x`方法に基づいて`square`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e7435-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="e7435-122">ポインターを合わせる場合`square`次を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7435-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="e7435-123">これは、関数の型のシグネチャと呼ばれるものです。</span><span class="sxs-lookup"><span data-stu-id="e7435-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="e7435-124">次のように読み取ることができます。"正方形をという名前の整数を受け取る関数は、x と整数が生成されます"。</span><span class="sxs-lookup"><span data-stu-id="e7435-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="e7435-125">コンパイラが付けた注`square`、`int`型今のところ、これは、乗算の間でジェネリックがないためには*すべて*型の場合ではなくジェネリック型の間では、します。</span><span class="sxs-lookup"><span data-stu-id="e7435-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="e7435-126">選択、F# コンパイラ`int`このポイントが調整されます型シグネチャを呼び出す場合`square`入力の種類などを変える、`float`します。</span><span class="sxs-lookup"><span data-stu-id="e7435-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="e7435-127">別の関数`main`が定義されているで装飾するが、 `EntryPoint` F# コンパイラにそのプログラムの実行を指示する属性を開始する必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="e7435-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="e7435-128">その他の場合と同じ規則に従って[C スタイルのプログラミング言語](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)コマンドライン引数は、この関数に渡すことができます、整数コードが返されます (通常`0`)。</span><span class="sxs-lookup"><span data-stu-id="e7435-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="e7435-129">このために呼び出される関数では、`square`関数の引数を持つ`12`します。</span><span class="sxs-lookup"><span data-stu-id="e7435-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="e7435-130">F#コンパイラの型が割り当てられます`square`する`int -> int`(を受け取る関数は、`int`を生成し、 `int`)。</span><span class="sxs-lookup"><span data-stu-id="e7435-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="e7435-131">呼び出し`printfn`を C スタイル プログラミング言語で、書式指定文字列で指定されている対応するパラメーターのような形式の文字列を使用して書式設定された印刷機能は、結果と、新しい行を出力します。</span><span class="sxs-lookup"><span data-stu-id="e7435-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="e7435-132">コードの実行</span><span class="sxs-lookup"><span data-stu-id="e7435-132">Running your code</span></span>

<span data-ttu-id="e7435-133">コードを実行してキーを押して、結果を参照してください**Ctrl**+**F5**します。</span><span class="sxs-lookup"><span data-stu-id="e7435-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="e7435-134">これにより、デバッグを行わずにプログラムを実行し、結果を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e7435-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="e7435-135">または、選択することができます、**デバッグ**トップレベル メニューの Visual Studio 内の項目し、選択**デバッグなしで開始**します。</span><span class="sxs-lookup"><span data-stu-id="e7435-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="e7435-136">次の Visual Studio のポップアップをコンソール ウィンドウに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7435-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="e7435-137">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="e7435-137">Congratulations!</span></span>  <span data-ttu-id="e7435-138">Visual Studio での初めての F# プロジェクトの作成、F# の関数は、この関数の呼び出しの結果を印刷を記述してプロジェクトを実行し、いくつかの結果を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7435-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7435-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7435-139">Next steps</span></span>

<span data-ttu-id="e7435-140">まだインストールしていない場合はチェック アウト、 [F# のツアー](../tour.md)、F# 言語のコア機能の一部が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7435-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="e7435-141">一部の F# の機能の概要が表示され Visual Studio にコピーして実行できる十分なコード サンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e7435-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="e7435-142">使用できますが、いくつかの優れた外部リソースがあるの紹介、 [F# ガイド](../index.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7435-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7435-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7435-143">See also</span></span>

- [<span data-ttu-id="e7435-144">F# のツアー</span><span class="sxs-lookup"><span data-stu-id="e7435-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="e7435-145">F#言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e7435-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="e7435-146">型の推論</span><span class="sxs-lookup"><span data-stu-id="e7435-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="e7435-147">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="e7435-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
