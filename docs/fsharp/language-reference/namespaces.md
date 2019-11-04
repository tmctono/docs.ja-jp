---
title: 名前空間
description: 名前F#空間を使用して、プログラム要素のグループに名前を添付できるようにすることで、関連する機能の領域にコードを整理する方法について説明します。
ms.date: 12/08/2018
ms.openlocfilehash: a55da1592b04c64576b4c66de61b5ca137289a6f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425042"
---
# <a name="namespaces"></a><span data-ttu-id="9288e-103">名前空間</span><span class="sxs-lookup"><span data-stu-id="9288e-103">Namespaces</span></span>

<span data-ttu-id="9288e-104">名前空間を使用すると、プログラム要素のF#グループに名前を付けることができるので、関連する機能の領域にコードを整理できます。</span><span class="sxs-lookup"><span data-stu-id="9288e-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="9288e-105">名前空間は、通常、ファイル内F#の最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="9288e-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="9288e-106">構文</span><span class="sxs-lookup"><span data-stu-id="9288e-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="9288e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9288e-107">Remarks</span></span>

<span data-ttu-id="9288e-108">名前空間にコードを配置する場合は、ファイルの最初の宣言で名前空間を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9288e-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="9288e-109">ファイル内に他の名前空間宣言が存在しない場合は、ファイル全体の内容が名前空間の一部になります。</span><span class="sxs-lookup"><span data-stu-id="9288e-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="9288e-110">その場合、次の名前空間宣言までのすべてのコードは、最初の名前空間内にあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="9288e-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="9288e-111">名前空間には、値と関数を直接含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="9288e-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="9288e-112">代わりに、値と関数をモジュールに含める必要があり、モジュールは名前空間に含まれています。</span><span class="sxs-lookup"><span data-stu-id="9288e-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="9288e-113">名前空間には、型、モジュールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9288e-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="9288e-114">XML ドキュメントコメントは名前空間の上に宣言できますが、無視されます。</span><span class="sxs-lookup"><span data-stu-id="9288e-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="9288e-115">コンパイラディレクティブは、名前空間の上に宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="9288e-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="9288e-116">名前空間は、namespace キーワードを使用して明示的に宣言することも、モジュールを宣言するときに暗黙的に宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="9288e-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="9288e-117">名前空間を明示的に宣言するには、namespace キーワードを使用し、その後に名前空間名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9288e-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="9288e-118">次の例は、型とその名前空間に含まれるモジュールを使用して `Widgets` 名前空間を宣言するコードファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="9288e-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="9288e-119">ファイルの内容全体が1つのモジュールに含まれている場合は、`module` キーワードを使用して、完全修飾モジュール名に新しい名前空間名を指定することで、名前空間を暗黙的に宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="9288e-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="9288e-120">次の例では、関数を含む名前空間 `Widgets` とモジュール `WidgetsModule`を宣言するコードファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="9288e-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="9288e-121">次のコードは、前のコードに相当しますが、モジュールはローカルモジュール宣言です。</span><span class="sxs-lookup"><span data-stu-id="9288e-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="9288e-122">この場合、名前空間は独自の行に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9288e-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="9288e-123">1つ以上の名前空間で同じファイルに複数のモジュールが必要な場合は、ローカルモジュール宣言を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9288e-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="9288e-124">ローカルモジュール宣言を使用する場合、モジュール宣言で修飾された名前空間を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9288e-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="9288e-125">次のコードは、名前空間宣言と2つのローカルモジュール宣言を含むファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="9288e-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="9288e-126">この場合、モジュールは名前空間に直接含まれています。ファイルと同じ名前を持つ、暗黙的に作成されたモジュールはありません。</span><span class="sxs-lookup"><span data-stu-id="9288e-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="9288e-127">ファイル内のその他のコード (`do` バインドなど) は名前空間にありますが、内部モジュールには存在しません。そのため、モジュール名を使用して `widgetFunction` モジュールメンバーを修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9288e-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="9288e-128">この例の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9288e-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="9288e-129">詳細については、「[モジュール](modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9288e-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="9288e-130">入れ子になった名前空間</span><span class="sxs-lookup"><span data-stu-id="9288e-130">Nested Namespaces</span></span>

<span data-ttu-id="9288e-131">入れ子になった名前空間を作成する場合は、完全修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9288e-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="9288e-132">それ以外の場合は、新しい最上位レベルの名前空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="9288e-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="9288e-133">名前空間の宣言では、インデントは無視されます。</span><span class="sxs-lookup"><span data-stu-id="9288e-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="9288e-134">次の例は、入れ子になった名前空間を宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9288e-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="9288e-135">ファイルとアセンブリ内の名前空間</span><span class="sxs-lookup"><span data-stu-id="9288e-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="9288e-136">名前空間は、1つのプロジェクトまたはコンパイルで複数のファイルにまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="9288e-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="9288e-137">*名前空間フラグメント*という用語は、1つのファイルに含まれる名前空間の部分を記述します。</span><span class="sxs-lookup"><span data-stu-id="9288e-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="9288e-138">名前空間は、複数のアセンブリにまたがることもできます。</span><span class="sxs-lookup"><span data-stu-id="9288e-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="9288e-139">たとえば、`System` 名前空間には、多数のアセンブリにまたがり、入れ子になった多数の名前空間が含まれている .NET Framework 全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9288e-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="9288e-140">グローバル名前空間</span><span class="sxs-lookup"><span data-stu-id="9288e-140">Global Namespace</span></span>

<span data-ttu-id="9288e-141">定義済みの名前空間 `global` を使用して、.NET の最上位レベルの名前空間に名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="9288e-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="9288e-142">また、グローバルを使用してトップレベルの .NET 名前空間を参照することもできます。たとえば、名前の競合を他の名前空間と解決するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9288e-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="9288e-143">再帰的な名前空間</span><span class="sxs-lookup"><span data-stu-id="9288e-143">Recursive namespaces</span></span>

<span data-ttu-id="9288e-144">また、含まれているすべてのコードが相互に再帰的になるように、名前空間を再帰として宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="9288e-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="9288e-145">これは `namespace rec`によって行われます。</span><span class="sxs-lookup"><span data-stu-id="9288e-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="9288e-146">`namespace rec` を使用すると、型とモジュール間で相互参照コードを記述できないという問題を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="9288e-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="9288e-147">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9288e-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

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

<span data-ttu-id="9288e-148">例外 `DontSqueezeTheBananaException` とクラス `Banana` 両方が相互に参照されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9288e-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="9288e-149">さらに、モジュール `BananaHelpers` とクラス `Banana` も相互に参照します。</span><span class="sxs-lookup"><span data-stu-id="9288e-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="9288e-150">`MutualReferences` 名前空間から `rec` キーワードをF#削除した場合、でを表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9288e-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="9288e-151">この機能は、最上位レベルの[モジュール](modules.md)でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9288e-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9288e-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="9288e-152">See also</span></span>

- [<span data-ttu-id="9288e-153">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="9288e-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9288e-154">モジュール</span><span class="sxs-lookup"><span data-stu-id="9288e-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="9288e-155">F#RFC FS-1009-ファイル内のより大きなスコープで相互参照型とモジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="9288e-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
