---
title: 'インポート宣言: open キーワード'
description: 完全修飾名を使用せずに参照できる要素を持つ F# インポート宣言し、モジュールまたは名前空間の指定方法について説明します。
ms.date: 04/04/2019
ms.openlocfilehash: 816bac551692c3397290f64c6267ee22e4ce90fb
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630574"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="79f8f-103">インポート宣言: `open` キーワード</span><span class="sxs-lookup"><span data-stu-id="79f8f-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="79f8f-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="79f8f-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="79f8f-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="79f8f-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="79f8f-106">*インポート宣言*は、完全修飾名を使用せずに参照できる要素を持つモジュールまたは名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="79f8f-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="79f8f-107">構文</span><span class="sxs-lookup"><span data-stu-id="79f8f-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="79f8f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="79f8f-108">Remarks</span></span>

<span data-ttu-id="79f8f-109">常に完全修飾名前空間またはモジュールパスを使用してコードを参照すると、書き込み、読み取り、および保守が困難なコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="79f8f-110">代わりに、頻繁に使用さ`open`れるモジュールと名前空間にキーワードを使用して、そのモジュールまたは名前空間のメンバーを参照するときに、完全修飾名の代わりに短い形式の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="79f8f-111">このキーワードはC#、 `using namespace`のキーワード`using` 、ビジュアルC++、および Visual Basic に似`Imports`ています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="79f8f-112">指定されたモジュールまたは名前空間は、同じプロジェクトまたは参照されるプロジェクトまたはアセンブリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f8f-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="79f8f-113">そうでない場合は、プロジェクトへの参照を追加するか、 `-reference`コマンド`-`ラインオプション`-r`(またはその省略形) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="79f8f-114">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f8f-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="79f8f-115">インポート宣言は、外側の名前空間、モジュール、またはファイルの末尾まで、宣言の後のコードで名前を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="79f8f-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="79f8f-116">複数のインポート宣言を使用する場合は、別々の行に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f8f-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="79f8f-117">次のコードは、 `open`キーワードを使用してコードを簡略化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="79f8f-118">複数F#の開いているモジュールまたは名前空間で同じ名前が発生した場合に、あいまいさが発生すると、コンパイラはエラーまたは警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="79f8f-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="79f8f-119">あいまいさが発生すると、F# より最近開いたモジュールまたは名前空間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="79f8f-120">たとえば、次の`empty`コードでは、 `List`と`Seq.empty` `Seq`の両方の`empty`モジュールにがある場合でも、はを意味します。</span><span class="sxs-lookup"><span data-stu-id="79f8f-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="79f8f-121">したがって、同じ名前を持つメンバーが含まれて`List` `Seq`いるモジュールまたは名前空間を開く場合は注意が必要です。代わりに、修飾名の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="79f8f-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="79f8f-122">コードがインポート宣言の順序に依存している状況を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f8f-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="79f8f-123">既定で開かれている名前空間</span><span class="sxs-lookup"><span data-stu-id="79f8f-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="79f8f-124">一部の名前空間は、これらの明示的なインポート宣言は必要ありませんが暗黙的に開かれた F# コードで頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="79f8f-125">次の表は、既定で開かれている名前空間を示しています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="79f8f-126">名前空間</span><span class="sxs-lookup"><span data-stu-id="79f8f-126">Namespace</span></span>|<span data-ttu-id="79f8f-127">説明</span><span class="sxs-lookup"><span data-stu-id="79f8f-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="79f8f-128">基本的な F# の型定義の組み込み型を含む`int`と`float`します。</span><span class="sxs-lookup"><span data-stu-id="79f8f-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="79f8f-129">`+` や`*`などの基本的な算術演算が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="79f8f-130">`List` や`Array`などの変更できないコレクションクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="79f8f-131">レイジー評価や非同期ワークフローなどのコントロール構成要素の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="79f8f-132">関数など、書式設定された`printf` IO 用の関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79f8f-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="79f8f-133">AutoOpen 属性</span><span class="sxs-lookup"><span data-stu-id="79f8f-133">AutoOpen Attribute</span></span>

<span data-ttu-id="79f8f-134">アセンブリが参照さ`AutoOpen`れたときに名前空間またはモジュールを自動的に開く場合は、アセンブリに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="79f8f-135">また、 `AutoOpen`属性をモジュールに適用して、親モジュールまたは名前空間を開いたときに自動的にそのモジュールを開くようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="79f8f-136">詳細については、「 [Core. AutoOpenAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f8f-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="79f8f-137">RequireQualifiedAccess 属性</span><span class="sxs-lookup"><span data-stu-id="79f8f-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="79f8f-138">一部のモジュール、レコード、または共用体型で`RequireQualifiedAccess`は、属性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="79f8f-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="79f8f-139">これらのモジュール、レコード、または共用体の要素を参照する場合は、インポート宣言を含めるかどうかに関係なく、修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f8f-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="79f8f-140">一般的に使用される名前を定義する型でこの属性を戦略的に使用すると、名前の競合を避けることができるため、ライブラリの変更に対するコードの回復性が向上します。</span><span class="sxs-lookup"><span data-stu-id="79f8f-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="79f8f-141">詳細については、「 [RequireQualifiedAccessAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79f8f-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="79f8f-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="79f8f-142">See also</span></span>

- [<span data-ttu-id="79f8f-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="79f8f-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="79f8f-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="79f8f-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="79f8f-145">モジュール</span><span class="sxs-lookup"><span data-stu-id="79f8f-145">Modules</span></span>](modules.md)
