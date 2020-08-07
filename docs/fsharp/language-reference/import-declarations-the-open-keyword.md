---
title: 'インポート宣言: open キーワード'
description: 'F # インポート宣言と、完全修飾名を使用せずに参照できる要素を持つモジュールまたは名前空間を指定する方法について説明します。'
ms.date: 04/04/2019
ms.openlocfilehash: 2b88427ca92212fb4a7598447dd1a5e12061093a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855089"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="111b7-103">インポート宣言: `open` キーワード</span><span class="sxs-lookup"><span data-stu-id="111b7-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="111b7-104">*インポート宣言*は、完全修飾名を使用せずに参照できる要素を持つモジュールまたは名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="111b7-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="111b7-105">構文</span><span class="sxs-lookup"><span data-stu-id="111b7-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="111b7-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="111b7-106">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="111b7-107">F # の docs.microsoft.com API リファレンスが完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="111b7-107">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="111b7-108">壊れたリンクが見つかった場合は、代わりに[F # コアライブラリのドキュメント](https://fsharp.github.io/fsharp-core-docs/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="111b7-108">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

<span data-ttu-id="111b7-109">常に完全修飾名前空間またはモジュールパスを使用してコードを参照すると、書き込み、読み取り、および保守が困難なコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="111b7-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="111b7-110">代わりに、 `open` 頻繁に使用されるモジュールと名前空間にキーワードを使用して、そのモジュールまたは名前空間のメンバーを参照するときに、完全修飾名の代わりに短い形式の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="111b7-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="111b7-111">このキーワードは、C# の `using` キーワード、 `using namespace` Visual C++、Visual Basic に似てい `Imports` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="111b7-112">指定されたモジュールまたは名前空間は、同じプロジェクトまたは参照されるプロジェクトまたはアセンブリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="111b7-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="111b7-113">そうでない場合は、プロジェクトへの参照を追加するか、 `-reference` コマンドラインオプション (またはその省略形) を使用することができ `-r` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="111b7-114">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="111b7-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="111b7-115">インポート宣言は、外側の名前空間、モジュール、またはファイルの末尾まで、宣言の後のコードで名前を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="111b7-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="111b7-116">複数のインポート宣言を使用する場合は、別々の行に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="111b7-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="111b7-117">次のコードは、キーワードを使用して `open` コードを簡略化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="111b7-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="111b7-118">F # コンパイラは、同じ名前が複数の開いているモジュールまたは名前空間で発生した場合に、あいまいさが発生した場合にエラーまたは警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="111b7-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="111b7-119">あいまいさが発生すると、F # は、最近開いたモジュールまたは名前空間を優先します。</span><span class="sxs-lookup"><span data-stu-id="111b7-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="111b7-120">たとえば、次のコードでは、 `empty` `Seq.empty` との `empty` 両方のモジュールにがある場合でも、はを意味し `List` `Seq` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="111b7-121">したがって、同じ名前を持つメンバーが含まれているモジュールまたは名前空間を開く場合は注意が必要です。 `List` `Seq` 代わりに、修飾名の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="111b7-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="111b7-122">コードがインポート宣言の順序に依存している状況を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="111b7-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="111b7-123">既定で開かれている名前空間</span><span class="sxs-lookup"><span data-stu-id="111b7-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="111b7-124">一部の名前空間は、明示的なインポート宣言がなくても暗黙的に開かれる F # コードでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="111b7-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="111b7-125">次の表は、既定で開かれている名前空間を示しています。</span><span class="sxs-lookup"><span data-stu-id="111b7-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="111b7-126">名前空間</span><span class="sxs-lookup"><span data-stu-id="111b7-126">Namespace</span></span>|<span data-ttu-id="111b7-127">説明</span><span class="sxs-lookup"><span data-stu-id="111b7-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="111b7-128">やなどの組み込み型の基本的な F # 型定義が含まれてい `int` `float` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="111b7-129">やなどの基本的な算術演算が含まれてい `+` `*` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="111b7-130">やなどの変更できないコレクションクラスが含まれてい `List` `Array` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="111b7-131">レイジー評価や非同期ワークフローなどのコントロール構成要素の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="111b7-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="111b7-132">関数など、書式設定された IO 用の関数が含まれてい `printf` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="111b7-133">AutoOpen 属性</span><span class="sxs-lookup"><span data-stu-id="111b7-133">AutoOpen Attribute</span></span>

<span data-ttu-id="111b7-134">`AutoOpen`アセンブリが参照されたときに名前空間またはモジュールを自動的に開く場合は、アセンブリに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="111b7-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="111b7-135">また、属性をモジュールに適用して、 `AutoOpen` 親モジュールまたは名前空間を開いたときに自動的にそのモジュールを開くようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="111b7-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="111b7-136">詳細については、「 [Core. AutoOpenAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="111b7-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="111b7-137">RequireQualifiedAccess 属性</span><span class="sxs-lookup"><span data-stu-id="111b7-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="111b7-138">一部のモジュール、レコード、または共用体型では、属性を指定でき `RequireQualifiedAccess` ます。</span><span class="sxs-lookup"><span data-stu-id="111b7-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="111b7-139">これらのモジュール、レコード、または共用体の要素を参照する場合は、インポート宣言を含めるかどうかに関係なく、修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="111b7-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="111b7-140">一般的に使用される名前を定義する型でこの属性を戦略的に使用すると、名前の競合を避けることができるため、ライブラリの変更に対するコードの回復性が向上します。</span><span class="sxs-lookup"><span data-stu-id="111b7-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="111b7-141">詳細については、「 [RequireQualifiedAccessAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="111b7-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="111b7-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="111b7-142">See also</span></span>

- [<span data-ttu-id="111b7-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="111b7-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="111b7-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="111b7-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="111b7-145">モジュール</span><span class="sxs-lookup"><span data-stu-id="111b7-145">Modules</span></span>](modules.md)
