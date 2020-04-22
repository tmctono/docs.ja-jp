---
title: 'インポート宣言: open キーワード'
description: F# インポート宣言と、完全修飾名を使用せずに参照できる要素を持つモジュールまたは名前空間を指定する方法について説明します。
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021533"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="54598-103">インポート宣言: `open` キーワード</span><span class="sxs-lookup"><span data-stu-id="54598-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="54598-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="54598-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="54598-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="54598-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="54598-106">*インポート宣言*は、完全修飾名を使用せずに参照できる要素を持つモジュールまたは名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="54598-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="54598-107">構文</span><span class="sxs-lookup"><span data-stu-id="54598-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="54598-108">解説</span><span class="sxs-lookup"><span data-stu-id="54598-108">Remarks</span></span>

<span data-ttu-id="54598-109">毎回完全修飾名前空間またはモジュール パスを使用してコードを参照すると、記述、読み取り、保守が困難なコードが作成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="54598-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="54598-110">代わりに、頻繁に`open`使用されるモジュールや名前空間にキーワードを使用すると、そのモジュールまたは名前空間のメンバーを参照するときに、完全修飾名の代わりに短い形式の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54598-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="54598-111">このキーワードは、C# `using` 、Visual C++、`using namespace`および Visual `Imports` Basic のキーワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="54598-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="54598-112">提供されるモジュールまたは名前空間は、同じプロジェクト内、または参照先のプロジェクトまたはアセンブリ内になければなりません。</span><span class="sxs-lookup"><span data-stu-id="54598-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="54598-113">参照が指定されていない場合は、プロジェクトへの参照を追加するか、`-reference`コマンド ライン オプション (または省略形`-r`) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54598-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="54598-114">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54598-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="54598-115">インポート宣言では、外側の名前空間、モジュール、またはファイルの末尾まで、宣言の後に記述されているコードで名前を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="54598-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="54598-116">複数のインポート宣言を使用する場合は、個別の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="54598-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="54598-117">次のコードは、コードを簡略化`open`するためにキーワードを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54598-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="54598-118">F# コンパイラは、複数の開いているモジュールまたは名前空間で同じ名前が発生したときにあいまいさが発生した場合に、エラーや警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="54598-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="54598-119">あいまいさが発生した場合、F# は、最近開いたモジュールまたは名前空間を優先します。</span><span class="sxs-lookup"><span data-stu-id="54598-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="54598-120">たとえば、次のコード`empty`では、 と`Seq.empty``empty``List``Seq`モジュールの両方に存在する場合でも、 を意味します。</span><span class="sxs-lookup"><span data-stu-id="54598-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="54598-121">したがって、同じ名前を持つメンバーを含む`List`、または`Seq`同じ名前を持つメンバーを含むモジュールまたは名前空間を開くときは注意が必要です。代わりに、修飾名の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="54598-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="54598-122">コードがインポート宣言の順序に依存する状況は避けてください。</span><span class="sxs-lookup"><span data-stu-id="54598-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="54598-123">既定で開かれている名前空間</span><span class="sxs-lookup"><span data-stu-id="54598-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="54598-124">一部の名前空間は F# コードで頻繁に使用されるため、明示的なインポート宣言を必要とせずに暗黙的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="54598-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="54598-125">次の表は、既定で開かれている名前空間を示しています。</span><span class="sxs-lookup"><span data-stu-id="54598-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="54598-126">名前空間</span><span class="sxs-lookup"><span data-stu-id="54598-126">Namespace</span></span>|<span data-ttu-id="54598-127">説明</span><span class="sxs-lookup"><span data-stu-id="54598-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="54598-128">などの組み込み型の基本的な F#`int`型`float`定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54598-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="54598-129">および などの`+`基本的な算術演算`*`が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54598-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="54598-130">および などの`List`変更できないコレクション クラスが`Array`含まれています。</span><span class="sxs-lookup"><span data-stu-id="54598-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="54598-131">遅延評価や非同期ワークフローなどのコントロール構成体の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54598-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="54598-132">書式付き IO 関数 (関数`printf`など) を格納します。</span><span class="sxs-lookup"><span data-stu-id="54598-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="54598-133">自動オープン属性</span><span class="sxs-lookup"><span data-stu-id="54598-133">AutoOpen Attribute</span></span>

<span data-ttu-id="54598-134">アセンブリが`AutoOpen`参照されるときに名前空間またはモジュールを自動的に開く場合は、アセンブリに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="54598-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="54598-135">また、親モジュールまたは`AutoOpen`名前空間を開いたときに、そのモジュールを自動的に開く属性をモジュールに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="54598-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="54598-136">詳細については[、「Core.AutoOpenAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54598-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="54598-137">必須アクセス属性が必要です</span><span class="sxs-lookup"><span data-stu-id="54598-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="54598-138">一部のモジュール、レコード、または共用体の`RequireQualifiedAccess`型では、属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="54598-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="54598-139">これらのモジュール、レコード、または共用体の要素を参照する場合は、インポート宣言を含めるかどうかに関係なく、修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54598-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="54598-140">この属性を、よく使用される名前を定義する型に戦略的に使用すると、名前の競合を避け、ライブラリの変更に対するコードの弾力性を高めます。</span><span class="sxs-lookup"><span data-stu-id="54598-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="54598-141">詳細については、「[クラスを必要とする」](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54598-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="54598-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="54598-142">See also</span></span>

- [<span data-ttu-id="54598-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="54598-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="54598-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="54598-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="54598-145">モジュール</span><span class="sxs-lookup"><span data-stu-id="54598-145">Modules</span></span>](modules.md)
