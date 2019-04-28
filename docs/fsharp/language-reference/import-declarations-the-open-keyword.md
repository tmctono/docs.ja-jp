---
title: インポート宣言:Open キーワード
description: 完全修飾名を使用せずに参照できる要素を持つ F# インポート宣言し、モジュールまたは名前空間の指定方法について説明します。
ms.date: 04/04/2019
ms.openlocfilehash: ad64190c3243c57a185f3b864270fca80590f079
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937502"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="4d751-103">インポート宣言:`open`キーワード</span><span class="sxs-lookup"><span data-stu-id="4d751-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="4d751-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d751-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="4d751-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="4d751-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="4d751-106">*インポート宣言*モジュールまたは名前空間完全修飾名を使用せずに参照できる要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d751-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d751-107">構文</span><span class="sxs-lookup"><span data-stu-id="4d751-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="4d751-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d751-108">Remarks</span></span>

<span data-ttu-id="4d751-109">名前空間またはモジュールの完全修飾パスを使用してコードを参照するたびには、書き込み、読み取り、および管理するが難しいコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4d751-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="4d751-110">代わりに、使用、`open`キーワードのモジュールや名前空間をそのモジュールまたは名前空間のメンバーを参照する場合は、完全修飾名ではなく、名前の短い形式を使用できるように頻繁に使用します。</span><span class="sxs-lookup"><span data-stu-id="4d751-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="4d751-111">このキーワードと似ています、 `using` c# でキーワード`using namespace`の Visual c と`Imports`Visual Basic でします。</span><span class="sxs-lookup"><span data-stu-id="4d751-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="4d751-112">モジュールまたは指定された名前空間は、同じプロジェクト内、または参照されるプロジェクトまたはアセンブリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d751-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="4d751-113">そうでない場合は、プロジェクトへの参照を追加またはを使用して、`-reference`コマンド`-`ライン オプション (またはその省略形、 `-r`)。</span><span class="sxs-lookup"><span data-stu-id="4d751-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="4d751-114">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d751-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="4d751-115">インポート宣言は、それを囲む名前空間、モジュール、またはファイルの最後までの宣言を次のコードで使用可能な名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d751-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="4d751-116">複数のインポート宣言を使用する場合は、別の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d751-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="4d751-117">次のコードは、使用、`open`キーワードをコードを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="4d751-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="4d751-118">F# 、同じ名前が 1 つ以上の開いているモジュールまたは名前空間で発生すると、あいまいさが発生した場合、コンパイラにエラーまたは警告を同時に生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4d751-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="4d751-119">あいまいさが発生すると、F# より最近開いたモジュールまたは名前空間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4d751-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="4d751-120">たとえば、次のコードで`empty`意味`Seq.empty`場合でも、`empty`両方である、`List`と`Seq`モジュール。</span><span class="sxs-lookup"><span data-stu-id="4d751-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="4d751-121">そのため、注意を開くときのモジュールまたは名前空間など`List`または`Seq`を含むメンバーの名前は同じでは、代わりに、修飾名の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="4d751-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="4d751-122">コードのインポート宣言の順序に依存するすべての状況を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d751-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="4d751-123">既定で開かれている名前空間</span><span class="sxs-lookup"><span data-stu-id="4d751-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="4d751-124">一部の名前空間は、これらの明示的なインポート宣言は必要ありませんが暗黙的に開かれた F# コードで頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d751-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="4d751-125">次の表では、既定で開かれている名前空間を示します。</span><span class="sxs-lookup"><span data-stu-id="4d751-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="4d751-126">名前空間</span><span class="sxs-lookup"><span data-stu-id="4d751-126">Namespace</span></span>|<span data-ttu-id="4d751-127">説明</span><span class="sxs-lookup"><span data-stu-id="4d751-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="4d751-128">基本的な F# の型定義の組み込み型を含む`int`と`float`します。</span><span class="sxs-lookup"><span data-stu-id="4d751-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="4d751-129">基本的な算術演算を含む`+`と`*`します。</span><span class="sxs-lookup"><span data-stu-id="4d751-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="4d751-130">変更できないコレクション クラスを含む`List`と`Array`します。</span><span class="sxs-lookup"><span data-stu-id="4d751-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="4d751-131">レイジー評価と非同期ワークフローなどのコントロール構成要素の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d751-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="4d751-132">などの書式設定された IO は、関数を含む、`printf`関数。</span><span class="sxs-lookup"><span data-stu-id="4d751-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="4d751-133">AutoOpen 属性</span><span class="sxs-lookup"><span data-stu-id="4d751-133">AutoOpen Attribute</span></span>

<span data-ttu-id="4d751-134">適用することができます、`AutoOpen`アセンブリに属性をアセンブリが参照されている場合に、名前空間またはモジュールが自動的に開きたい場合。</span><span class="sxs-lookup"><span data-stu-id="4d751-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="4d751-135">適用することも、`AutoOpen`親モジュールまたは名前空間が開かれるときに、そのモジュールを自動的に開くモジュールに属性します。</span><span class="sxs-lookup"><span data-stu-id="4d751-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="4d751-136">詳細については、次を参照してください。 [Core.AutoOpenAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="4d751-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="4d751-137">RequireQualifiedAccess 属性</span><span class="sxs-lookup"><span data-stu-id="4d751-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="4d751-138">一部のモジュール、レコード、または共用体の型を指定できます、`RequireQualifiedAccess`属性。</span><span class="sxs-lookup"><span data-stu-id="4d751-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="4d751-139">これらのモジュール、レコード、または共用体の要素を参照する場合は、インポート宣言を含めるかどうかに関係なく、修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d751-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="4d751-140">この属性を戦略的に使用する場合は、よくを定義する型名を使用する、役立つように名前の競合を回避し、コードより回復力のあるライブラリの変更に。</span><span class="sxs-lookup"><span data-stu-id="4d751-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="4d751-141">詳細については、次を参照してください。 [Core.RequireQualifiedAccessAttribute クラス](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)します。</span><span class="sxs-lookup"><span data-stu-id="4d751-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d751-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d751-142">See also</span></span>

- [<span data-ttu-id="4d751-143">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="4d751-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4d751-144">名前空間</span><span class="sxs-lookup"><span data-stu-id="4d751-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="4d751-145">モジュール</span><span class="sxs-lookup"><span data-stu-id="4d751-145">Modules</span></span>](modules.md)
