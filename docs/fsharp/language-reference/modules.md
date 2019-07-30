---
title: モジュール
description: F# のモジュールの値、型、および F# のプログラム内の関数値などの F# コードでのグループ化の方法について説明します。
ms.date: 04/24/2017
ms.openlocfilehash: 685ab638e7e1b6c8d47d1a316483abcc18e40199
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627432"
---
# <a name="modules"></a><span data-ttu-id="78f45-103">モジュール</span><span class="sxs-lookup"><span data-stu-id="78f45-103">Modules</span></span>

<span data-ttu-id="78f45-104">F# 言語のコンテキストで、*モジュール*値、型、および F# のプログラム内の関数値などの F# コードでのグループです。</span><span class="sxs-lookup"><span data-stu-id="78f45-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="78f45-105">モジュールのコードをグループ化すると、関連するコードをまとめることができ、プログラム内で名前の競合を回避するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="78f45-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="78f45-106">構文</span><span class="sxs-lookup"><span data-stu-id="78f45-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="78f45-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="78f45-107">Remarks</span></span>

<span data-ttu-id="78f45-108">F# のモジュールは、型、値、関数の値のコードなどの F# コード構造のグループ化`do`バインドします。</span><span class="sxs-lookup"><span data-stu-id="78f45-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="78f45-109">静的メンバーのみを持つ共通言語ランタイム (CLR) クラスとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="78f45-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="78f45-110">モジュール宣言には、ファイル全体がモジュールに含まれるかどうかに応じて、最上位のモジュール宣言とローカルモジュール宣言の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="78f45-111">最上位レベルのモジュール宣言には、モジュール内のファイル全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78f45-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="78f45-112">最上位レベルのモジュール宣言は、ファイル内の最初の宣言としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="78f45-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="78f45-113">最上位のモジュール宣言の構文では、省略可能な*修飾名前空間*は、モジュールを含む入れ子になった名前空間の名前のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="78f45-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="78f45-114">修飾された名前空間は、事前に宣言されている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78f45-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="78f45-115">最上位のモジュールで宣言にインデントを付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78f45-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="78f45-116">ローカルモジュール内のすべての宣言をインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="78f45-117">ローカルモジュール宣言では、そのモジュール宣言の下でインデントされた宣言のみがモジュールの一部になります。</span><span class="sxs-lookup"><span data-stu-id="78f45-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="78f45-118">コードファイルが最上位のモジュール宣言または名前空間宣言で開始されていない場合、ローカルモジュールを含め、ファイルの内容全体が、ファイルと同じ名前を持つ、暗黙的に作成された最上位レベルのモジュールの一部になります。拡張子はありません。最初の文字を大文字に変換したもの。</span><span class="sxs-lookup"><span data-stu-id="78f45-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="78f45-119">たとえば、次のファイルについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="78f45-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="78f45-120">このファイルは、次のように記述されているかのようにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="78f45-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="78f45-121">ファイルに複数のモジュールがある場合は、モジュールごとにローカルモジュール宣言を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="78f45-122">外側の名前空間が宣言されている場合、これらのモジュールは外側の名前空間の一部になります。</span><span class="sxs-lookup"><span data-stu-id="78f45-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="78f45-123">外側の名前空間が宣言されていない場合、これらのモジュールは、暗黙的に作成された最上位レベルのモジュールの一部になります。</span><span class="sxs-lookup"><span data-stu-id="78f45-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="78f45-124">次のコード例は、複数のモジュールを含むコードファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="78f45-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="78f45-125">コンパイラは`Multiplemodules` `MyModule2` 、という名前のトップレベルモジュールを暗黙的に作成し、その最上位モジュールに入れ子になっています。`MyModule1`</span><span class="sxs-lookup"><span data-stu-id="78f45-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="78f45-126">1つのプロジェクトまたは1つのコンパイルに複数のファイルがある場合、またはライブラリをビルドする場合は、ファイルの先頭に名前空間宣言またはモジュール宣言を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="78f45-127">のみ、F# コンパイラは暗黙的にモジュール名を決定し、プロジェクトやコンパイルのコマンド ラインに 1 つのみのファイルは、アプリケーションを作成するときにします。</span><span class="sxs-lookup"><span data-stu-id="78f45-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="78f45-128">*アクセシビリティ修飾子*は`public`、 `private`、、 `internal`のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="78f45-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="78f45-129">詳細については、「[Access Control](access-control.md)」(アクセス制御) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f45-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="78f45-130">既定値はパブリックです。</span><span class="sxs-lookup"><span data-stu-id="78f45-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="78f45-131">参照 (モジュールのコードを)</span><span class="sxs-lookup"><span data-stu-id="78f45-131">Referencing Code in Modules</span></span>

<span data-ttu-id="78f45-132">別のモジュールから関数、型、および値を参照する場合は、修飾名を使用するか、モジュールを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="78f45-133">修飾名を使用する場合は、名前空間、モジュール、および必要なプログラム要素の識別子を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="78f45-134">修飾されたパスの各部分は、次のようにドット (.) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="78f45-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="78f45-135">モジュールまたは1つ以上の名前空間を開いて、コードを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="78f45-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="78f45-136">名前空間とモジュールを開く方法の詳細に[ついては、「宣言のインポート」を参照してください。`open`キーワード](import-declarations-the-open-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="78f45-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="78f45-137">次のコード例は、ファイルの末尾までのすべてのコードを含む最上位のモジュールを示しています。</span><span class="sxs-lookup"><span data-stu-id="78f45-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="78f45-138">同じプロジェクト内の別のファイルからこのコードを使用するには、次の例に示すように、修飾名を使用するか、または関数を使用する前にモジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="78f45-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="78f45-139">入れ子になったモジュール</span><span class="sxs-lookup"><span data-stu-id="78f45-139">Nested Modules</span></span>

<span data-ttu-id="78f45-140">モジュールは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="78f45-140">Modules can be nested.</span></span> <span data-ttu-id="78f45-141">内部モジュールは、新しいモジュールではなく内部モジュールであることを示すために、外部モジュール宣言と同じようにインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="78f45-142">たとえば、次の2つの例を比較します。</span><span class="sxs-lookup"><span data-stu-id="78f45-142">For example, compare the following two examples.</span></span> <span data-ttu-id="78f45-143">モジュール`Z`は、次のコードの内部モジュールです。</span><span class="sxs-lookup"><span data-stu-id="78f45-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="78f45-144">ただし、 `Z`モジュールは次のコード`Y`のモジュールの兄弟です。</span><span class="sxs-lookup"><span data-stu-id="78f45-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="78f45-145">モジュールは、モジュール`Y`内の他の宣言と同じようにインデントされないため、次のコードの兄弟モジュールでもあります。 `Z`</span><span class="sxs-lookup"><span data-stu-id="78f45-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="78f45-146">最後に、外側のモジュールに宣言がなく、その後に別のモジュール宣言が直後にある場合、新しいモジュール宣言は内部モジュールと見なされますが、2番目のモジュール定義が次の値よりも多くインデントされていない場合は、コンパイラによって警告が表示されます。まずは。</span><span class="sxs-lookup"><span data-stu-id="78f45-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="78f45-147">警告を回避するには、内側のモジュールをインデントします。</span><span class="sxs-lookup"><span data-stu-id="78f45-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="78f45-148">ファイル内のすべてのコードを1つの外部モジュールに配置し、内部モジュールを使用する場合、外側のモジュールでは等号を必要とせず、外側のモジュールで使用される内部モジュール宣言を含む宣言をインデントする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78f45-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="78f45-149">内部モジュール宣言内の宣言は、インデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f45-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="78f45-150">次のコードはこのケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="78f45-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="78f45-151">再帰的なモジュール</span><span class="sxs-lookup"><span data-stu-id="78f45-151">Recursive modules</span></span>

<span data-ttu-id="78f45-152">F#4.1 では、含まれているすべてのコードを相互に再帰的に使用できるモジュールの概念が導入されています。</span><span class="sxs-lookup"><span data-stu-id="78f45-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="78f45-153">これは、を`module rec`使用して行います。</span><span class="sxs-lookup"><span data-stu-id="78f45-153">This is done via `module rec`.</span></span>  <span data-ttu-id="78f45-154">を使用`module rec`すると、型とモジュール間で相互参照コードを記述できないという問題を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="78f45-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="78f45-155">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78f45-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
    type Orientation = Up | Down
    type PeelState = Peeled | Unpeeled

    // This exception depends on the type below.
    exception DontSqueezeTheBananaException of Banana

    type BananaPeel() = class end

    type Banana(orientation : Orientation) =
        member val IsPeeled = false with get, set
        member val Orientation = orientation with get, set
        member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

        member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
        member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

    module BananaHelpers =
        let peel (b: Banana) =
            let flip (banana: Banana) =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides (banana: Banana) =
                banana.Sides
                |> List.map (function
                             | Unpeeled -> Peeled
                             | Peeled -> Peeled)

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

<span data-ttu-id="78f45-156">例外`DontSqueezeTheBananaException`とクラス`Banana`は両方とも参照していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78f45-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="78f45-157">さらに、モジュール`BananaHelpers`とクラス`Banana`も相互に参照します。</span><span class="sxs-lookup"><span data-stu-id="78f45-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="78f45-158">これは、削除した場合、F# で表現できませんが、`rec`からキーワード、`RecursiveModule`モジュール。</span><span class="sxs-lookup"><span data-stu-id="78f45-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="78f45-159">この機能はでも[名前空間](namespaces.md)F# 4.1 とします。</span><span class="sxs-lookup"><span data-stu-id="78f45-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="78f45-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="78f45-160">See also</span></span>

- [<span data-ttu-id="78f45-161">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="78f45-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="78f45-162">名前空間</span><span class="sxs-lookup"><span data-stu-id="78f45-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="78f45-163">F#RFC FS-1009-ファイル内のより大きなスコープで相互参照型とモジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="78f45-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
