---
title: 名前空間
description: 学習方法、F#名前空間では、プログラム要素のグループに名前を追加することによって関連する機能の領域にコードを整理できます。
ms.date: 12/08/2018
ms.openlocfilehash: 526d7a07e4804751811c15fa91b0c74c1954d591
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666392"
---
# <a name="namespaces"></a><span data-ttu-id="35c92-103">名前空間</span><span class="sxs-lookup"><span data-stu-id="35c92-103">Namespaces</span></span>

<span data-ttu-id="35c92-104">名前空間では、関連する機能の領域にへのグループに名前を追加できるコードを編成できます。F#プログラム要素です。</span><span class="sxs-lookup"><span data-stu-id="35c92-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="35c92-105">名前空間は、通常の最上位の要素でF#ファイル。</span><span class="sxs-lookup"><span data-stu-id="35c92-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="35c92-106">構文</span><span class="sxs-lookup"><span data-stu-id="35c92-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="35c92-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="35c92-107">Remarks</span></span>

<span data-ttu-id="35c92-108">名前空間にコードを配置する場合は、ファイル内の最初の宣言は名前空間を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c92-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="35c92-109">ファイル全体の内容は、名前空間の一部となる、ファイルにさらにその他の名前空間宣言が存在しない指定します。</span><span class="sxs-lookup"><span data-stu-id="35c92-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="35c92-110">場合は、[次へ] の名前空間宣言までのすべてのコードは最初の名前空間内にあると見なさします。</span><span class="sxs-lookup"><span data-stu-id="35c92-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="35c92-111">値および関数、名前空間を含める直接ことはできません。</span><span class="sxs-lookup"><span data-stu-id="35c92-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="35c92-112">代わりに、モジュールでは、値および関数を含める必要があるし、モジュールの名前空間に含まれます。</span><span class="sxs-lookup"><span data-stu-id="35c92-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="35c92-113">名前空間は、モジュールの種類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="35c92-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="35c92-114">名前空間の上、XML ドキュメント コメントを宣言できますが、無視されます。</span><span class="sxs-lookup"><span data-stu-id="35c92-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="35c92-115">コンパイラ ディレクティブは、名前空間の上にも宣言できます。</span><span class="sxs-lookup"><span data-stu-id="35c92-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="35c92-116">名前空間は明示的に宣言する名前空間キーワード、または暗黙的にモジュールを宣言するときに。</span><span class="sxs-lookup"><span data-stu-id="35c92-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="35c92-117">名前空間を明示的に宣言するには、名前空間キーワードの後に名前空間の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="35c92-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="35c92-118">次の例では、名前空間を宣言するコード ファイル`Widgets`型とその名前空間に含まれるモジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="35c92-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="35c92-119">ファイルの内容全体が 1 つのモジュールである場合は、宣言することも名前空間に暗黙的を使用して、`module`キーワードとモジュールの完全修飾名で新しい名前空間名を指定します。</span><span class="sxs-lookup"><span data-stu-id="35c92-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="35c92-120">次の例では、名前空間を宣言するコード ファイル`Widgets`とモジュール`WidgetsModule`関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35c92-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="35c92-121">次のコードは上記のコードと同じですが、モジュールがローカル モジュールの宣言。</span><span class="sxs-lookup"><span data-stu-id="35c92-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="35c92-122">その場合は、名前空間は、独自の行に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c92-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="35c92-123">1 つ以上のモジュールが 1 つまたは複数の名前空間で同じファイルで必要に応じて、ローカル モジュール宣言を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c92-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="35c92-124">モジュールのローカル宣言を使用する場合は、モジュール宣言で修飾名前空間を使用できません。</span><span class="sxs-lookup"><span data-stu-id="35c92-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="35c92-125">次のコードでは、名前空間の宣言と 2 つのモジュールのローカル宣言を持つファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="35c92-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="35c92-126">この場合、モジュールが、名前空間で直接に含まれるファイルと同じ名前を持つ、暗黙的に作成されたモジュールはありません。</span><span class="sxs-lookup"><span data-stu-id="35c92-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="35c92-127">などのファイルで、コードの他の`do`モジュール メンバーを修飾する必要があるため、内部のモジュールではなく、名前空間には、バインド、`widgetFunction`モジュール名を使用しています。</span><span class="sxs-lookup"><span data-stu-id="35c92-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="35c92-128">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35c92-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="35c92-129">詳細については、次を参照してください。[モジュール](modules.md)します。</span><span class="sxs-lookup"><span data-stu-id="35c92-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="35c92-130">入れ子になった名前空間</span><span class="sxs-lookup"><span data-stu-id="35c92-130">Nested Namespaces</span></span>

<span data-ttu-id="35c92-131">入れ子になった名前空間を作成するときに、完全修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c92-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="35c92-132">それ以外の場合、新しい最上位レベルの名前空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="35c92-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="35c92-133">インデントは、名前空間の宣言では無視されます。</span><span class="sxs-lookup"><span data-stu-id="35c92-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="35c92-134">次の例では、入れ子になった名前空間を宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35c92-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="35c92-135">ファイルとアセンブリの名前空間</span><span class="sxs-lookup"><span data-stu-id="35c92-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="35c92-136">名前空間は、1 つのプロジェクトやコンパイルで複数のファイルにまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="35c92-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="35c92-137">用語*名前空間のフラグメント*1 つのファイルに含まれている名前空間の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="35c92-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="35c92-138">名前空間は、複数のアセンブリをまたがることもできます。</span><span class="sxs-lookup"><span data-stu-id="35c92-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="35c92-139">たとえば、`System`名前空間に多数のアセンブリにまたがり、多数の入れ子になった名前空間が含まれていますが、全体の .NET Framework が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35c92-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="35c92-140">グローバル Namespace</span><span class="sxs-lookup"><span data-stu-id="35c92-140">Global Namespace</span></span>

<span data-ttu-id="35c92-141">定義済みの名前空間を使用する`global`に最上位レベルの .NET 名前空間に名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="35c92-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="35c92-142">使用することできますもグローバル他の名前空間と名前が競合を解決するのには、たとえば最上位レベルの .NET 名前空間を参照します。</span><span class="sxs-lookup"><span data-stu-id="35c92-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="35c92-143">再帰的な名前空間</span><span class="sxs-lookup"><span data-stu-id="35c92-143">Recursive namespaces</span></span>

<span data-ttu-id="35c92-144">名前空間は、再帰的に相互に含まれているすべてのコードを許可するには、再帰的なとしても宣言できます。</span><span class="sxs-lookup"><span data-stu-id="35c92-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="35c92-145">使用してこれには`namespace rec`します。</span><span class="sxs-lookup"><span data-stu-id="35c92-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="35c92-146">使用`namespace rec`されない型とモジュール間の相互参照コードを記述することでいくつかの問題を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="35c92-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="35c92-147">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="35c92-147">The following is an example of this:</span></span>

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

<span data-ttu-id="35c92-148">なお、例外`DontSqueezeTheBananaException`とクラス`Banana`両方には、互いを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35c92-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="35c92-149">モジュールではさらに、`BananaHelpers`とクラス`Banana`も互いに参照してください。</span><span class="sxs-lookup"><span data-stu-id="35c92-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="35c92-150">表現することがあるF#を削除した場合、`rec`からキーワード、`MutualReferences`名前空間。</span><span class="sxs-lookup"><span data-stu-id="35c92-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="35c92-151">この機能は使用できる最上位[モジュール](modules.md)します。</span><span class="sxs-lookup"><span data-stu-id="35c92-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35c92-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="35c92-152">See also</span></span>

- [<span data-ttu-id="35c92-153">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="35c92-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="35c92-154">モジュール</span><span class="sxs-lookup"><span data-stu-id="35c92-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="35c92-155">F#RFC FS-1009 - ファイル内でより大きな範囲経由で相互に参照型とモジュールを許可します。</span><span class="sxs-lookup"><span data-stu-id="35c92-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)