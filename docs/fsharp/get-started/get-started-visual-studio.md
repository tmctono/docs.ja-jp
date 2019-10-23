---
title: Visual Studioで F# をはじめよう
description: Visual Studio で F# を使用する方法について説明します。
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082699"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="aeccc-103">Visual Studioで F# をはじめよう</span><span class="sxs-lookup"><span data-stu-id="aeccc-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="aeccc-104">F# および Visual F# ツールは、Visual Studio IDE でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="aeccc-105">作業を開始できることを確認します。 [Visual Studio をインストール F#](install-fsharp.md#install-f-with-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="aeccc-106">コンソールアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="aeccc-106">Creating a console application</span></span>

<span data-ttu-id="aeccc-107">Visual Studio の最も基本的なプロジェクトの 1 つは、コンソールアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="aeccc-108">これを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-108">Here's how to do it.</span></span>  <span data-ttu-id="aeccc-109">Visual Studio を開いたら、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="aeccc-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="aeccc-110">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeccc-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="aeccc-111">[プロジェクト] ダイアログで、新規で**テンプレート**、はず**Visual F#** します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="aeccc-112">テンプレートを表示するにF#は、これを選択します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="aeccc-113">**.Net Core コンソールアプリ**または**コンソールアプリ**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="aeccc-114">**OK** ボタンを選択して、F# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="aeccc-115">ソリューション エクスプ ローラーに F# プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="aeccc-116">コードの記述</span><span class="sxs-lookup"><span data-stu-id="aeccc-116">Writing your code</span></span>

<span data-ttu-id="aeccc-117">まず、コードをいくつか記述してみましょう。</span><span class="sxs-lookup"><span data-stu-id="aeccc-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="aeccc-118">`Program.fs`ファイルが開いていることを確認し、その内容を次の内容に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="aeccc-119">前のコードサンプルでは、`x`という名前の入力を受け取り、それを単独で乗算する関数`square`が定義されています。</span><span class="sxs-lookup"><span data-stu-id="aeccc-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="aeccc-120">F#は[型推定](../language-reference/type-inference.md) を行うため、`x`の型を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aeccc-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="aeccc-121">F# コンパイラは乗算が有効な型を認識し、`square`の呼び出しに基づいて`x` に型を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="aeccc-122">マウスポインターを`square`に合わせると、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="aeccc-123">これは、関数の型シグネチャとして知られています。</span><span class="sxs-lookup"><span data-stu-id="aeccc-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="aeccc-124">次のように読み取ることができます。"Square は、x という整数を受け取り、整数を生成する関数です。</span><span class="sxs-lookup"><span data-stu-id="aeccc-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="aeccc-125">コンパイラ`square`によって型が`int`設定されていることに注意してください。これは、乗算が*すべて*の型のジェネリックではなく、閉じられた型のセット全体でジェネリックであるためです。</span><span class="sxs-lookup"><span data-stu-id="aeccc-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="aeccc-126">選択、F# コンパイラ`int`このポイントが調整されます型シグネチャを呼び出す場合`square`入力の種類などを変える、`float`します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="aeccc-127">別の関数`main`が定義されているで装飾するが、 `EntryPoint` F# コンパイラにそのプログラムの実行を指示する属性を開始する必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="aeccc-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="aeccc-128">これは、コマンドライン引数をこの関数に渡すことができる他の[C スタイルのプログラミング言語](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)と同じ規則に従い、整数のコードが返され`0`ます (通常は)。</span><span class="sxs-lookup"><span data-stu-id="aeccc-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="aeccc-129">この関数は、 `square` `12`引数を指定して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="aeccc-130">コンパイラF#は、の`square`型をに`int -> int`割り当てます。これ`int`は、を受け取り、を生成`int`する関数です。</span><span class="sxs-lookup"><span data-stu-id="aeccc-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="aeccc-131">の呼び出し`printfn`は、書式指定文字列を使用する書式設定された印刷関数で、C スタイルのプログラミング言語に似ています。また、書式指定文字列で指定されたパラメーターに対応するパラメーターを使用して、結果と改行を出力します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="aeccc-132">コードの実行</span><span class="sxs-lookup"><span data-stu-id="aeccc-132">Running your code</span></span>

<span data-ttu-id="aeccc-133">**Ctrl**+**F5**キーを押してコードを実行し、結果を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="aeccc-134">これにより、デバッグなしでプログラムが実行され、結果を確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="aeccc-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="aeccc-135">または、Visual Studio で **[デバッグ]** トップレベルメニュー項目を選択し、 **[デバッグなしで開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeccc-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="aeccc-136">次のように、Visual Studio がポップアップ表示されたコンソールウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="aeccc-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="aeccc-137">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="aeccc-137">Congratulations!</span></span>  <span data-ttu-id="aeccc-138">Visual Studioで最初の F# プロジェクトを作成し、その関数の呼び出し結果を出力する F# 関数を作成し、プロジェクトを実行して結果を確認しました。</span><span class="sxs-lookup"><span data-stu-id="aeccc-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aeccc-139">次のステップ</span><span class="sxs-lookup"><span data-stu-id="aeccc-139">Next steps</span></span>

<span data-ttu-id="aeccc-140">まだインストールしていない場合は、F# 言語のコア機能の一部をカバーする[F# のツアー](../tour.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aeccc-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="aeccc-141">F# の機能の一部の概要を示し、Visual Studio にコピーして実行できる十分なコード サンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="aeccc-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="aeccc-142">[F# ガイド](../index.md) で紹介されている、優れた外部リソースもあります。</span><span class="sxs-lookup"><span data-stu-id="aeccc-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aeccc-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="aeccc-143">See also</span></span>

- [<span data-ttu-id="aeccc-144">F# のツアー</span><span class="sxs-lookup"><span data-stu-id="aeccc-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="aeccc-145">F#言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="aeccc-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="aeccc-146">型推論</span><span class="sxs-lookup"><span data-stu-id="aeccc-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="aeccc-147">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="aeccc-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
