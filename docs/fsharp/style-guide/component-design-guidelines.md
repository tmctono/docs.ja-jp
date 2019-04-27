---
title: F#コンポーネントのデザイン ガイドライン
description: 他の呼び出し元で消費するための F# コンポーネントを記述するためのガイドラインについて説明します。
ms.date: 05/14/2018
ms.openlocfilehash: c61e4cd9098388b356c71c325d66c760fa866cf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902162"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="16c28-103">F#コンポーネントのデザイン ガイドライン</span><span class="sxs-lookup"><span data-stu-id="16c28-103">F# component design guidelines</span></span>

<span data-ttu-id="16c28-104">このドキュメントは、一連の F# プログラミング、F# コンポーネント デザインのガイドラインに基づいて、v14、Microsoft Research のコンポーネントのデザイン ガイドラインと[別バージョン](https://fsharp.org/specs/component-design-guidelines/)curated を最初におよび、F# Software Foundation によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="16c28-105">このドキュメントでは、F# プログラミングに慣れてを前提としています。</span><span class="sxs-lookup"><span data-stu-id="16c28-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="16c28-106">多くの貢献と、このガイドのさまざまなバージョンに役立つフィードバック F# コミュニティに協力してくれたします。</span><span class="sxs-lookup"><span data-stu-id="16c28-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="16c28-107">概要</span><span class="sxs-lookup"><span data-stu-id="16c28-107">Overview</span></span>

<span data-ttu-id="16c28-108">このドキュメントは、F# コンポーネント デザインおよびコーディングに関連する問題の一部を検索します。</span><span class="sxs-lookup"><span data-stu-id="16c28-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="16c28-109">コンポーネントは、次のいずれかに意味があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="16c28-110">そのプロジェクト内の外部のコンシューマーを持つ F# プロジェクトのレイヤー。</span><span class="sxs-lookup"><span data-stu-id="16c28-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="16c28-111">ライブラリ アセンブリ境界を越えて F# コードで使用量のためのものです。</span><span class="sxs-lookup"><span data-stu-id="16c28-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="16c28-112">ライブラリ アセンブリ境界を越えて任意の .NET 言語で使用量のためのものです。</span><span class="sxs-lookup"><span data-stu-id="16c28-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="16c28-113">など、パッケージ リポジトリを使用して配布するためのもので、ライブラリ[NuGet](https://nuget.org)します。</span><span class="sxs-lookup"><span data-stu-id="16c28-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="16c28-114">この記事で説明した手法に従う、[優れた F# コードの 5 つの原則](index.md#five-principles-of-good-f-code)、およびため両方の機能を利用し、適切なプログラミング オブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="16c28-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="16c28-115">方法論に関係なくコンポーネントとライブラリのデザイナーのさまざまな実用的で prosaic 問題に直面して、開発者が最も簡単に使用できる API を作成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="16c28-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="16c28-116">Conscientious アプリケーションの[.NET ライブラリのデザイン ガイドライン](../../standard/design-guidelines/index.md)を使用する快適な api の一貫性のあるセットを作成するを進めるためされます。</span><span class="sxs-lookup"><span data-stu-id="16c28-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="16c28-117">一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="16c28-117">General guidelines</span></span>

<span data-ttu-id="16c28-118">適用されるいくつかのユニバーサル ガイドラインがあるF#ライブラリ、ライブラリの対象となるユーザーに関係なく。</span><span class="sxs-lookup"><span data-stu-id="16c28-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="16c28-119">.NET ライブラリのデザイン ガイドラインについて説明します</span><span class="sxs-lookup"><span data-stu-id="16c28-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="16c28-120">種類に関係なくのF#コーディングを行うの実務知識を持ちすることが重要、 [.NET ライブラリのデザイン ガイドライン](../../standard/design-guidelines/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="16c28-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="16c28-121">ほとんどの他の F# および .NET プログラマは、次のガイドラインに習熟しに準拠するように .NET コードを期待します。</span><span class="sxs-lookup"><span data-stu-id="16c28-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="16c28-122">.NET ライブラリのデザイン ガイドラインは、名前付け、クラス、インターフェイス、メンバーのデザイン (プロパティ、メソッド、イベントなど) およびの詳細は、設計に関する一般的なガイダンスを提供し、さまざまな設計ガイダンスの参照の最初のポイントを便利なはします。</span><span class="sxs-lookup"><span data-stu-id="16c28-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="16c28-123">XML ドキュメントのコメントをコードに追加します。</span><span class="sxs-lookup"><span data-stu-id="16c28-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="16c28-124">パブリック Api での XML ドキュメントでは、ライブラリのファイルをこれらの型とメンバー、および有効にするドキュメントの構築に使用するときに、優れたの Intellisense とクイック ヒントを取得できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16c28-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="16c28-125">参照してください、 [XML ドキュメント](../language-reference/xml-documentation.md)内で、xmldoc コメントの追加のマークアップを使用できるさまざまな xml タグの概要。</span><span class="sxs-lookup"><span data-stu-id="16c28-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="16c28-126">短い形式のいずれかの XML コメントを使用することができます (`/// comment`)、または標準の XML コメント (`///<summary>comment</summary>`)。</span><span class="sxs-lookup"><span data-stu-id="16c28-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="16c28-127">安定したライブラリと Api のコンポーネントの明示的な署名ファイル (.fsi) の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="16c28-128">明示的な署名ファイルを使用して、F#ライブラリは、どちらも、ライブラリのサーフェスのパブリック ドキュメント間を明確に分離を提供し、内部の完全な公開がわかっていることを確認するのには、パブリック API の簡潔な概要を提供します。実装の詳細。</span><span class="sxs-lookup"><span data-stu-id="16c28-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="16c28-129">シグネチャ ファイルが実装と署名の両方のファイルに対する変更を要求することによって、パブリック API を変更する際の問題を追加することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="16c28-130">その結果、署名ファイルを通常のみ際に挿入される API 確固たるものになりますが、大幅に変更される予定ですされなくします。</span><span class="sxs-lookup"><span data-stu-id="16c28-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="16c28-131">常に .NET で文字列を使用するためのベスト プラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="16c28-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="16c28-132">次の[.NET で文字列を使用するためのベスト プラクティス](../../standard/base-types/best-practices-strings.md)ガイダンス。</span><span class="sxs-lookup"><span data-stu-id="16c28-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="16c28-133">具体的には、常に明示的に状態*文化的なインテント*変換と文字列の比較 (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="16c28-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="16c28-134">に関するガイドラインF#-ライブラリに接続します。</span><span class="sxs-lookup"><span data-stu-id="16c28-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="16c28-135">このセクションでは、パブリック F# を開発するための推奨事項を表示します-ライブラリ; に接続します。F# 開発者が使用するためのパブリック Api を公開するライブラリは、します。</span><span class="sxs-lookup"><span data-stu-id="16c28-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="16c28-136">具体的には適用可能なさまざまなライブラリ デザインの推奨事項がありますF#します。</span><span class="sxs-lookup"><span data-stu-id="16c28-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="16c28-137">特定の推奨事項がない場合、.NET ライブラリのデザイン ガイドラインは、フォールバックのガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="16c28-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="16c28-138">名前付け規則</span><span class="sxs-lookup"><span data-stu-id="16c28-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="16c28-139">.NET の名前付けおよび大文字と小文字の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="16c28-140">次の表では、.NET の名前付けおよび大文字と小文字の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="16c28-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="16c28-141">あることが小さな追加F#を構築します。</span><span class="sxs-lookup"><span data-stu-id="16c28-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="16c28-142">構成体</span><span class="sxs-lookup"><span data-stu-id="16c28-142">Construct</span></span> | <span data-ttu-id="16c28-143">Case</span><span class="sxs-lookup"><span data-stu-id="16c28-143">Case</span></span> | <span data-ttu-id="16c28-144">パーツ</span><span class="sxs-lookup"><span data-stu-id="16c28-144">Part</span></span> | <span data-ttu-id="16c28-145">使用例</span><span class="sxs-lookup"><span data-stu-id="16c28-145">Examples</span></span> | <span data-ttu-id="16c28-146">メモ</span><span class="sxs-lookup"><span data-stu-id="16c28-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="16c28-147">具象型</span><span class="sxs-lookup"><span data-stu-id="16c28-147">Concrete types</span></span> | <span data-ttu-id="16c28-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-148">PascalCase</span></span> | <span data-ttu-id="16c28-149">名詞または形容詞</span><span class="sxs-lookup"><span data-stu-id="16c28-149">Noun/ adjective</span></span> | <span data-ttu-id="16c28-150">一覧で、Double、複雑な</span><span class="sxs-lookup"><span data-stu-id="16c28-150">List, Double, Complex</span></span> | <span data-ttu-id="16c28-151">具象型は、構造体、クラス、列挙、デリゲート、レコード、および共用体です。</span><span class="sxs-lookup"><span data-stu-id="16c28-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="16c28-152">型名が小文字従来 OCaml には、F# 型の .NET の名前付けスキームは採用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="16c28-153">DLL</span><span class="sxs-lookup"><span data-stu-id="16c28-153">DLLs</span></span>           | <span data-ttu-id="16c28-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-154">PascalCase</span></span> |                 | <span data-ttu-id="16c28-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="16c28-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="16c28-156">共用体タグ</span><span class="sxs-lookup"><span data-stu-id="16c28-156">Union tags</span></span>     | <span data-ttu-id="16c28-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-157">PascalCase</span></span> | <span data-ttu-id="16c28-158">名詞</span><span class="sxs-lookup"><span data-stu-id="16c28-158">Noun</span></span> | <span data-ttu-id="16c28-159">いくつかの追加、成功</span><span class="sxs-lookup"><span data-stu-id="16c28-159">Some, Add, Success</span></span> | <span data-ttu-id="16c28-160">パブリック Api では、プレフィックスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="16c28-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="16c28-161">必要に応じてときなど、内部プレフィックスを使用します。 `type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="16c28-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="16c28-162">event</span><span class="sxs-lookup"><span data-stu-id="16c28-162">Event</span></span>          | <span data-ttu-id="16c28-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-163">PascalCase</span></span> | <span data-ttu-id="16c28-164">動詞</span><span class="sxs-lookup"><span data-stu-id="16c28-164">Verb</span></span> | <span data-ttu-id="16c28-165">ValueChanged/ValueChanging</span><span class="sxs-lookup"><span data-stu-id="16c28-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="16c28-166">例外</span><span class="sxs-lookup"><span data-stu-id="16c28-166">Exceptions</span></span>     | <span data-ttu-id="16c28-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-167">PascalCase</span></span> |      | <span data-ttu-id="16c28-168">WebException</span><span class="sxs-lookup"><span data-stu-id="16c28-168">WebException</span></span> | <span data-ttu-id="16c28-169">名前は、"Exception"で終わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-169">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="16c28-170">フィールド</span><span class="sxs-lookup"><span data-stu-id="16c28-170">Field</span></span>          | <span data-ttu-id="16c28-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-171">PascalCase</span></span> | <span data-ttu-id="16c28-172">名詞</span><span class="sxs-lookup"><span data-stu-id="16c28-172">Noun</span></span> | <span data-ttu-id="16c28-173">CurrentName</span><span class="sxs-lookup"><span data-stu-id="16c28-173">CurrentName</span></span>  | |
| <span data-ttu-id="16c28-174">インターフェイス型</span><span class="sxs-lookup"><span data-stu-id="16c28-174">Interface types</span></span> |  <span data-ttu-id="16c28-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-175">PascalCase</span></span> | <span data-ttu-id="16c28-176">名詞または形容詞</span><span class="sxs-lookup"><span data-stu-id="16c28-176">Noun/ adjective</span></span> | <span data-ttu-id="16c28-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="16c28-177">IDisposable</span></span> | <span data-ttu-id="16c28-178">名前は、"I"で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-178">Name should start with “I”.</span></span> |
| <span data-ttu-id="16c28-179">メソッド</span><span class="sxs-lookup"><span data-stu-id="16c28-179">Method</span></span> |  <span data-ttu-id="16c28-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-180">PascalCase</span></span> |  <span data-ttu-id="16c28-181">動詞</span><span class="sxs-lookup"><span data-stu-id="16c28-181">Verb</span></span> | <span data-ttu-id="16c28-182">ToString</span><span class="sxs-lookup"><span data-stu-id="16c28-182">ToString</span></span> | |
| <span data-ttu-id="16c28-183">名前空間</span><span class="sxs-lookup"><span data-stu-id="16c28-183">Namespace</span></span> | <span data-ttu-id="16c28-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-184">PascalCase</span></span> | | <span data-ttu-id="16c28-185">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="16c28-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="16c28-186">一般的に使用して`<Organization>.<Technology>[.<Subnamespace>]`、ただし、テクノロジは、組織の独立した場合、組織を削除します。</span><span class="sxs-lookup"><span data-stu-id="16c28-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="16c28-187">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16c28-187">Parameters</span></span> | <span data-ttu-id="16c28-188">キャメル ケース</span><span class="sxs-lookup"><span data-stu-id="16c28-188">camelCase</span></span> | <span data-ttu-id="16c28-189">名詞</span><span class="sxs-lookup"><span data-stu-id="16c28-189">Noun</span></span> |  <span data-ttu-id="16c28-190">typeName、変換、範囲</span><span class="sxs-lookup"><span data-stu-id="16c28-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="16c28-191">(内部) の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-191">let values (internal)</span></span> | <span data-ttu-id="16c28-192">キャメル ケースまたは PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-192">camelCase or PascalCase</span></span> | <span data-ttu-id="16c28-193">名詞と動詞</span><span class="sxs-lookup"><span data-stu-id="16c28-193">Noun/ verb</span></span> |  <span data-ttu-id="16c28-194">getValue、myTable</span><span class="sxs-lookup"><span data-stu-id="16c28-194">getValue, myTable</span></span> |
| <span data-ttu-id="16c28-195">値 (外部) の使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-195">let values (external)</span></span> | <span data-ttu-id="16c28-196">キャメル ケースまたは PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-196">camelCase or PascalCase</span></span> | <span data-ttu-id="16c28-197">名詞と動詞</span><span class="sxs-lookup"><span data-stu-id="16c28-197">Noun/verb</span></span>  | <span data-ttu-id="16c28-198">List.map、Dates.Today</span><span class="sxs-lookup"><span data-stu-id="16c28-198">List.map, Dates.Today</span></span> | <span data-ttu-id="16c28-199">let バインドされた値は、従来の機能の設計パターンに従うときに多くの場合、パブリック。</span><span class="sxs-lookup"><span data-stu-id="16c28-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="16c28-200">ただし、一般に PascalCase とき使用識別子は、他の .NET 言語から使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c28-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="16c28-201">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16c28-201">Property</span></span>  | <span data-ttu-id="16c28-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="16c28-202">PascalCase</span></span>  | <span data-ttu-id="16c28-203">名詞または形容詞</span><span class="sxs-lookup"><span data-stu-id="16c28-203">Noun/ adjective</span></span>  | <span data-ttu-id="16c28-204">IsEndOfFile、背景色</span><span class="sxs-lookup"><span data-stu-id="16c28-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="16c28-205">ブール型プロパティ一般的に使用されできます IsEndOfFile、IsNotEndOfFile しないように、肯定を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="16c28-206">省略形を回避します。</span><span class="sxs-lookup"><span data-stu-id="16c28-206">Avoid abbreviations</span></span>

<span data-ttu-id="16c28-207">.NET のガイドラインの省略形の使用を防ぐため (たとえば、"を使用して、`OnButtonClick`なく`OnBtnClick`")。</span><span class="sxs-lookup"><span data-stu-id="16c28-207">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="16c28-208">共通の省略形など`Async`「非同期」の場合は許容されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-208">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="16c28-209">このガイドラインは関数型プログラミング; も無視されます。たとえば、 `List.iter` 「反復処理する」の省略形を使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="16c28-210">このため、略語を使用して F# のより充実を許容する傾向があります-に-F# プログラミングでは、まだ一般にパブリック コンポーネントのデザインに避ける必要がありますが、します。</span><span class="sxs-lookup"><span data-stu-id="16c28-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="16c28-211">大文字小文字の区別、名前の衝突を避ける</span><span class="sxs-lookup"><span data-stu-id="16c28-211">Avoid casing name collisions</span></span>

<span data-ttu-id="16c28-212">.NET のガイドラインには、一部のクライアント言語 (Visual Basic など) は大文字であるために、名前の競合を解消するために単独で大文字小文字の区別を使用できないことがあるとします。</span><span class="sxs-lookup"><span data-stu-id="16c28-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="16c28-213">適切な場所、頭字語を使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="16c28-214">XML などの頭字語は、省略形でないや、uncapitalized 形式 (Xml) での .NET ライブラリで広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="16c28-215">のみ広く認識させ、よく知られた頭字語を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="16c28-216">PascalCase を使用して、ジェネリック パラメーター名</span><span class="sxs-lookup"><span data-stu-id="16c28-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="16c28-217">などのパブリック Api でのジェネリック パラメーターの名前を PascalCase を使用しないでくださいF#-ライブラリに接続します。</span><span class="sxs-lookup"><span data-stu-id="16c28-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="16c28-218">ような名前を使用して、具体的には、 `T`、 `U`、 `T1`、`T2`の任意のジェネリック パラメーターを使用して特定の名前は合理的で、し、F# のライブラリに接続するような名前を使用して、 `Key`、 `Value`、 `Arg`(ただし、たとえばいない`TKey`)。</span><span class="sxs-lookup"><span data-stu-id="16c28-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="16c28-219">PascalCase またはキャメル ケースのいずれかを使用して、パブリック関数および F# モジュール内の値</span><span class="sxs-lookup"><span data-stu-id="16c28-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="16c28-220">キャメル ケースが使用するように設計されたパブリック関数の使用非修飾 (たとえば、 `invalidArg`)、および (List.map など) の「標準的なコレクション関数」。</span><span class="sxs-lookup"><span data-stu-id="16c28-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="16c28-221">どちらの場合も、関数名は言語のキーワードのようにずっと機能します。</span><span class="sxs-lookup"><span data-stu-id="16c28-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="16c28-222">オブジェクト、型、およびモジュールの設計</span><span class="sxs-lookup"><span data-stu-id="16c28-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="16c28-223">名前空間またはモジュールを使用して、型とモジュール</span><span class="sxs-lookup"><span data-stu-id="16c28-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="16c28-224">コンポーネントでそれぞれの F# ファイルの名前空間の宣言またはモジュールの宣言のいずれかで開始します。</span><span class="sxs-lookup"><span data-stu-id="16c28-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="16c28-225">または</span><span class="sxs-lookup"><span data-stu-id="16c28-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="16c28-226">モジュールや名前空間を使用して、最上位レベルのコードを整理する間の相違点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16c28-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="16c28-227">名前空間が複数のファイルにまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="16c28-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="16c28-228">内部のモジュール内である場合を除いて、名前空間は F# の関数を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="16c28-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="16c28-229">単一ファイル内の特定のモジュールのコードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="16c28-230">最上位レベルのモジュールが内部のモジュールを必要としないの F# 関数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="16c28-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="16c28-231">最上位レベルの名前空間またはモジュールの間で choice では、コードのコンパイル済みの形式に影響し、したがってが影響他の .NET 言語で表示する必要があります API 最終的に使用する F# コードの外部に。</span><span class="sxs-lookup"><span data-stu-id="16c28-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="16c28-232">メソッドとプロパティを使用して、オブジェクトの種類に固有の操作</span><span class="sxs-lookup"><span data-stu-id="16c28-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="16c28-233">オブジェクトを使用する場合は、メソッドとプロパティをその型として使用できる機能が実装されることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="16c28-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="16c28-234">必要があります、必ずしも、メンバーに実装していないメンバーについては、機能の大部分が機能を使用できる部分にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="16c28-235">クラスを使用して、変更可能な状態をカプセル化</span><span class="sxs-lookup"><span data-stu-id="16c28-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="16c28-236">F#、これだけ行う必要がある場所、状態は既にカプセル化されていないクロージャ、シーケンス式、または非同期計算などの別の言語コンストラクトです。</span><span class="sxs-lookup"><span data-stu-id="16c28-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="16c28-237">インターフェイスを使用してグループ化に関連する操作</span><span class="sxs-lookup"><span data-stu-id="16c28-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="16c28-238">インターフェイスの種類を使用して、一連の操作を表します。</span><span class="sxs-lookup"><span data-stu-id="16c28-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="16c28-239">関数の組などの関数のレコードの他のオプションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="16c28-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="16c28-240">優先。</span><span class="sxs-lookup"><span data-stu-id="16c28-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="16c28-241">インターフェイスは、.net では、何ファンクターは通常表示を実現するために使用できる最上級の概念です。</span><span class="sxs-lookup"><span data-stu-id="16c28-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="16c28-242">さらに、関数のレコードのことはできませんが、プログラムに移った型のエンコードに使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c28-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="16c28-243">コレクションの操作を実行するグループの機能をモジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-243">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="16c28-244">コレクション型を定義するときになどの操作の標準セットを提供することを検討してください`CollectionType.map`と`CollectionType.iter`) の新しいコレクション型。</span><span class="sxs-lookup"><span data-stu-id="16c28-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="16c28-245">このようなモジュールを含める場合は FSharp.Core の関数の名前付け規則に従います。</span><span class="sxs-lookup"><span data-stu-id="16c28-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="16c28-246">特にで数値演算と DSL ライブラリの一般的な正規の関数グループの機能をモジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="16c28-247">たとえば、`Microsoft.FSharp.Core.Operators`は、自動的に開かれているコレクションの最上位の関数です (など`abs`と`sin`) FSharp.Core.dll によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="16c28-248">同様に、統計ライブラリが関数を持つモジュールを含めることがあります`erf`と`erfc`を明示的にまたは自動的に開くこのモジュールは設計されています。</span><span class="sxs-lookup"><span data-stu-id="16c28-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="16c28-249">RequireQualifiedAccess の使用を検討し、慎重に AutoOpen 属性を適用</span><span class="sxs-lookup"><span data-stu-id="16c28-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="16c28-250">追加、`[<RequireQualifiedAccess>]`属性をモジュールには、モジュールが開かれていないことと、アクセスを修飾するモジュールの要素への参照が明示的に必要なことを示します。</span><span class="sxs-lookup"><span data-stu-id="16c28-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="16c28-251">たとえば、`Microsoft.FSharp.Collections.List`モジュールにはこの属性があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="16c28-252">これは、機能は、関数と、モジュール内の値は、他のモジュール名と競合する可能性のある名前を持つ場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="16c28-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="16c28-253">修飾のアクセスを必要とすると、長期的な保守容易性とライブラリの発展が大幅に向上できます。</span><span class="sxs-lookup"><span data-stu-id="16c28-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="16c28-254">追加、`[<AutoOpen>]`モジュールに属性が含まれる名前空間が開かれたときに、モジュールが開かれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="16c28-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="16c28-255">`[<AutoOpen>]`属性は、アセンブリ、アセンブリが参照されている場合に自動的に開かれているモジュールを示すためにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="16c28-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="16c28-256">統計ライブラリではたとえば、 **MathsHeaven.Statistics**含めることができます、`module MathsHeaven.Statistics.Operators`関数を含む`erf`と`erfc`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="16c28-257">このモジュールとしてマークするが妥当`[<AutoOpen>]`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="16c28-258">つまり、`open MathsHeaven.Statistics`もがこのモジュールを開き、名前を`erf`と`erfc`スコープにします。</span><span class="sxs-lookup"><span data-stu-id="16c28-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="16c28-259">別なを使用して、`[<AutoOpen>]`拡張メソッドが含まれるモジュールです。</span><span class="sxs-lookup"><span data-stu-id="16c28-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="16c28-260">多用する`[<AutoOpen>]`汚染の名前空間と属性に潜在顧客を注意して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="16c28-261">特定のドメインを賢く利用で特定のライブラリの`[<AutoOpen>]`ユーザビリティは向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="16c28-262">よく知られている演算子を使用して、適切なクラスで演算子メンバーの定義を検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="16c28-263">場合によってベクトルなどの数学的構造をモデル化するクラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="16c28-264">モデル化されるドメインによく知られている演算子がある場合、クラスに固有のメンバーとして定義することお勧めします。</span><span class="sxs-lookup"><span data-stu-id="16c28-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="16c28-265">このガイダンスは、このような種類の一般的な .NET ガイダンスに対応します。</span><span class="sxs-lookup"><span data-stu-id="16c28-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="16c28-266">ただし、F# コードこれにより、これらの型の F# 関数と組み合わせておよび List.sumBy などのメンバー制約でのメソッドで使用するようにさらに重要ですができます。</span><span class="sxs-lookup"><span data-stu-id="16c28-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="16c28-267">提供する CompiledName の使用を検討します。その他の .NET 言語のコンシューマーの NET のわかりやすい名前</span><span class="sxs-lookup"><span data-stu-id="16c28-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="16c28-268">名前が必要な 1 つのスタイルをする場合がありますF#コンシューマー (などを小文字で静的メンバー モジュール連結関数の場合と同様) がアセンブリにコンパイルすると、名前の別のスタイルが。</span><span class="sxs-lookup"><span data-stu-id="16c28-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="16c28-269">使用することができます、`[<CompiledName>]`非 F# アセンブリを使用するコードのさまざまなスタイルを指定する属性。</span><span class="sxs-lookup"><span data-stu-id="16c28-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="16c28-270">使用して`[<CompiledName>]`、非 F# アセンブリのコンシューマー向けの .NET の名前付け規則を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="16c28-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="16c28-271">メンバー関数の場合は、メソッドのオーバー ロードを使用するため、これによりより単純な API の場合</span><span class="sxs-lookup"><span data-stu-id="16c28-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="16c28-272">メソッドのオーバー ロードは、さまざまなオプションや引数が、同様の機能を実行する必要がある API を簡略化するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="16c28-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="16c28-273">F#、引数の型ではなく、引数の数にオーバー ロードする方が一般的です。</span><span class="sxs-lookup"><span data-stu-id="16c28-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="16c28-274">これらの型のデザインが発展する可能性がある場合、レコード、共用体の型の表現を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="16c28-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="16c28-275">オブジェクトの具体的な表現に表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="16c28-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="16c28-276">具体的な表現など<xref:System.DateTime>値は .NET ライブラリの設計の外部、パブリック API によって公開されません。</span><span class="sxs-lookup"><span data-stu-id="16c28-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="16c28-277">実行時に、共通言語ランタイムは、実行全体で使用されるコミットの実装を認識します。</span><span class="sxs-lookup"><span data-stu-id="16c28-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="16c28-278">ただし、コンパイル済みのコードはしない自体具体的な表現への依存関係を選択します。</span><span class="sxs-lookup"><span data-stu-id="16c28-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="16c28-279">機能拡張の実装の継承は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="16c28-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="16c28-280">F#、実装の継承はほとんど使用しません。</span><span class="sxs-lookup"><span data-stu-id="16c28-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="16c28-281">さらに、継承階層は多くの場合、複雑で、新しい要件が到着したときに変更が困難にします。</span><span class="sxs-lookup"><span data-stu-id="16c28-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="16c28-282">継承の実装は、互換性を維持し、まれなケースで、問題に最適なソリューションですが、インターフェイスの実装などのポリモーフィズムの設計時に、F# プログラムで代替手法を検索する必要があります F# でも存在します。</span><span class="sxs-lookup"><span data-stu-id="16c28-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="16c28-283">関数とメンバーのシグネチャ</span><span class="sxs-lookup"><span data-stu-id="16c28-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="16c28-284">複数の関連のない値の数が少ないを返すときに、戻り値のタプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="16c28-285">戻り値の型で組を使用する良い例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16c28-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="16c28-286">多くのコンポーネントを含む型を返すかを特定できる単一のエンティティには、コンポーネントが関係する場合は、タプルではなく名前付きの型を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="16c28-287">使用`Async<T>`F# API の境界での非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="16c28-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="16c28-288">という名前の対応する同期操作があるかどうかは`Operation`を返す、 `T`、非同期操作を指定する必要がありますし、`AsyncOperation`返された場合`Async<T>`または`OperationAsync`返された場合`Task<T>`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="16c28-289">Begin/end のメソッドを公開に一般的な .NET 型を使用を検討してください`Async.FromBeginEnd`.NET Api を F# 非同期プログラミング モデルを提供するファサードとして拡張メソッドを記述します。</span><span class="sxs-lookup"><span data-stu-id="16c28-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="16c28-290">例外</span><span class="sxs-lookup"><span data-stu-id="16c28-290">Exceptions</span></span>

<span data-ttu-id="16c28-291">参照してください[エラー管理](conventions.md#error-management)に、例外、結果、およびオプションの適切な使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="16c28-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="16c28-292">拡張メンバー</span><span class="sxs-lookup"><span data-stu-id="16c28-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="16c28-293">F# での F# の拡張メンバーを注意深く適用-に-F# コンポーネント</span><span class="sxs-lookup"><span data-stu-id="16c28-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="16c28-294">F#拡張メンバーは、通常のみ使用のほとんどの使用のモードの種類に関連付けられた組み込みの操作のクロージャに含まれる操作。</span><span class="sxs-lookup"><span data-stu-id="16c28-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="16c28-295">一般的な用途の 1 つはさまざまな .NET 型の F# 慣用 Api を提供することです。</span><span class="sxs-lookup"><span data-stu-id="16c28-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="16c28-296">共用体の型</span><span class="sxs-lookup"><span data-stu-id="16c28-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="16c28-297">判別共用体をクラスの階層構造ではなくツリー構造のデータの使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="16c28-298">ツリー状の構造体は、定義されている再帰的にします。</span><span class="sxs-lookup"><span data-stu-id="16c28-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="16c28-299">これは、継承、厄介なが判別共用体で洗練されました。</span><span class="sxs-lookup"><span data-stu-id="16c28-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="16c28-300">判別共用体のツリーのようなデータを表すではパターン マッチングで exhaustiveness からメリットを得ることもできます。</span><span class="sxs-lookup"><span data-stu-id="16c28-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="16c28-301">使用`[<RequireQualifiedAccess>]`で名前を持つケースが十分に一意でない共用体の型</span><span class="sxs-lookup"><span data-stu-id="16c28-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="16c28-302">同じ名前が判別された共用体ケースなどのさまざまなもののわかりやすい名前をドメインでわかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="16c28-303">使用することができます`[<RequireQualifiedAccess>]`トリガーの順序に依存にシャドウによる混乱を招くエラーを回避するために名前の大文字と小文字を区別する`open`ステートメント</span><span class="sxs-lookup"><span data-stu-id="16c28-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="16c28-304">これらの型のデザインが発展する可能性がある場合、バイナリの互換性のある Api の判別共用体の表現を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="16c28-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="16c28-305">共用体の型は、F# のパターンに一致するフォームの簡潔なプログラミング モデルに依存します。</span><span class="sxs-lookup"><span data-stu-id="16c28-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="16c28-306">前述のように、これらの型のデザインが発展する可能性がある場合は、具体的なデータ表現を漏洩を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="16c28-307">プライベートまたは内部の宣言を使用して判別共用体の表現を隠すことが、または署名ファイルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="16c28-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="16c28-308">判別共用体を無差別に開示する場合した方のバージョンにハード ライブラリ ユーザー コードを損なうことがなく。</span><span class="sxs-lookup"><span data-stu-id="16c28-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="16c28-309">代わりに、型の値に一致するパターンを許可するように 1 つまたは複数のアクティブ パターンを明らかに検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="16c28-310">アクティブ パターンでは、F# 共用体の型を直接公開することを回避しながらに一致するパターンを F# でコンシューマーに提供する別の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="16c28-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="16c28-311">インライン関数とメンバー制約</span><span class="sxs-lookup"><span data-stu-id="16c28-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="16c28-312">暗黙的なメンバー制約とジェネリック型を静的に解決されるインライン関数を使用して、汎用的な数値アルゴリズムを定義します。</span><span class="sxs-lookup"><span data-stu-id="16c28-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="16c28-313">算術メンバー制約と F# 比較の制約は、F# プログラミングの標準です。</span><span class="sxs-lookup"><span data-stu-id="16c28-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="16c28-314">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="16c28-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="16c28-315">この関数の型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16c28-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="16c28-316">これは、数値演算ライブラリ内のパブリック API の適切な関数です。</span><span class="sxs-lookup"><span data-stu-id="16c28-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="16c28-317">型のクラスとアヒル型定義をシミュレートするためにメンバー制約は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="16c28-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="16c28-318">「ダック タイピング」をシミュレートすることは F# メンバー制約を使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-318">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="16c28-319">ただし、メンバーを使用してこのにない全般を F# で使用する必要があります-に-F# ライブラリ設計します。</span><span class="sxs-lookup"><span data-stu-id="16c28-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="16c28-320">これは、未知または標準の暗黙的な制約に基づいてライブラリ設計を強いと特定のフレームワークを 1 つのパターンに関連付けられていますが、ユーザー コードが発生する傾向があるためにです。</span><span class="sxs-lookup"><span data-stu-id="16c28-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="16c28-321">さらに、非常に長いコンパイル時間の結果としてこの方法でメンバーの制約を頻繁に使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="16c28-322">演算子の定義</span><span class="sxs-lookup"><span data-stu-id="16c28-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="16c28-323">シンボリック カスタムの演算子を定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="16c28-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="16c28-324">カスタム演算子はいくつかの状況で不可欠な実装コードの大きな本文内で非常に有用な表記のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="16c28-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="16c28-325">ライブラリの新しいユーザーの名前付きの関数は使いやすく多くの場合です。</span><span class="sxs-lookup"><span data-stu-id="16c28-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="16c28-326">さらに、ユーザーを検索演算子、IDE と検索エンジンの既存の制限のためのヘルプを検索することが難しく、シンボリック カスタムの演算子をドキュメントにハードことができます。</span><span class="sxs-lookup"><span data-stu-id="16c28-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="16c28-327">その結果、名前付きの関数と、メンバーとして、機能を公開し、表記の利点がありますが、ドキュメントと cognitive コストのことを上回る場合にのみ、この機能のための演算子をさらに公開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="16c28-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="16c28-328">測定単位</span><span class="sxs-lookup"><span data-stu-id="16c28-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="16c28-329">追加された型の安全性の測定単位を使用して、慎重にF#コード</span><span class="sxs-lookup"><span data-stu-id="16c28-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="16c28-330">他の .NET 言語で表示したときに、メジャーの単位の追加入力情報が消去されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="16c28-331">.NET コンポーネント、ツール、およびリフレクションは型-san の単位で表示されますが注意します。</span><span class="sxs-lookup"><span data-stu-id="16c28-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="16c28-332">たとえば、c# のコンシューマーが表示されます`float`なく`float<kg>`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="16c28-333">型略称</span><span class="sxs-lookup"><span data-stu-id="16c28-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="16c28-334">型の省略形を使用して慎重に F# コードを簡略化</span><span class="sxs-lookup"><span data-stu-id="16c28-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="16c28-335">.NET コンポーネント、ツール、およびリフレクションでは、型の省略名は表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="16c28-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="16c28-336">型の省略形の使用量を大幅には、ドメインの表示よりも複雑になるほど実際には、コンシューマーが混乱することもできます。</span><span class="sxs-lookup"><span data-stu-id="16c28-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="16c28-337">メンバーとプロパティが省略されている型で使用するものは本質的に異なる必要がありますのパブリック型の型の省略形を回避します。</span><span class="sxs-lookup"><span data-stu-id="16c28-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="16c28-338">この場合、省略されている型は定義されている実際の型の表現についてはあまりが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="16c28-339">代わりに、クラス型または単一ケースの判別共用体の省略形の折り返しを検討してください (または、パフォーマンスが重要な場合は、構造体の型を使用して省略形をラップすることを検討してください)。</span><span class="sxs-lookup"><span data-stu-id="16c28-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="16c28-340">たとえば、複数のマップの例の F# マップの特殊なケースとして定義することも考えは。</span><span class="sxs-lookup"><span data-stu-id="16c28-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="16c28-341">ただし、この種類でドット表記の論理操作でないマップでの操作と同じ – たとえば、lookup 操作にマップする妥当なは。[キー] に返された例外を発生させるのではなく、辞書にキーがない場合は、空のリスト。</span><span class="sxs-lookup"><span data-stu-id="16c28-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="16c28-342">他の .NET 言語から使用するためのライブラリのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16c28-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="16c28-343">他の .NET 言語から使用するためのライブラリを設計するときに準拠する重要なは、 [.NET ライブラリのデザイン ガイドライン](../../standard/design-guidelines/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="16c28-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="16c28-344">このドキュメントでは、これらのライブラリを F# ではなく、標準の .NET ライブラリとしてラベル付けします。-F# を使用してライブラリに接続する、制限なく構築します。</span><span class="sxs-lookup"><span data-stu-id="16c28-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="16c28-345">Vanilla .NET ライブラリのデザインには、F# の使用を最小限に抑えることで親しみやすく、慣用 Api の .NET Framework の残りの部分と一貫性を提供することを意味のパブリック API で特定のコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="16c28-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="16c28-346">ルールは、次のセクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="16c28-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="16c28-347">(他の .NET 言語から使用するためのライブラリ) の Namespace および型の設計</span><span class="sxs-lookup"><span data-stu-id="16c28-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="16c28-348">コンポーネントのパブリック API を .NET の名前付け規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="16c28-349">省略名と、.NET の大文字と小文字のガイドラインを使用する特別な注意してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="16c28-350">主要な組織構造として、コンポーネントの名前空間、型、およびメンバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="16c28-351">パブリックな機能を含むすべてのファイルで始まり、`namespace`宣言、および名前空間でのみパブリックに公開されたエンティティに、型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c28-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="16c28-352">使用しないF#モジュール。</span><span class="sxs-lookup"><span data-stu-id="16c28-352">Do not use F# modules.</span></span>

<span data-ttu-id="16c28-353">実装コード、ユーティリティの種類、およびユーティリティ関数を保持するのにには、パブリックでないモジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="16c28-354">静的な型に優先されますモジュールを可能になる API の今後の進化 F# モジュール内で使用することはできませんをオーバー ロード、およびその他の .NET API 設計概念を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="16c28-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="16c28-355">たとえば、次のパブリック API: の代わりに</span><span class="sxs-lookup"><span data-stu-id="16c28-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="16c28-356">代わりに検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="16c28-357">型のデザインが進化しない場合は、バニラ .NET Api で F# レコード型を使用してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="16c28-358">F#レコードの種類は、単純な .NET クラスをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="16c28-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="16c28-359">これらは Api のいくつか単純で安定した型に適しています。</span><span class="sxs-lookup"><span data-stu-id="16c28-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="16c28-360">使用を検討する必要があります、`[<NoEquality>]`と`[<NoComparison>]`インターフェイスの自動生成を抑制する属性。</span><span class="sxs-lookup"><span data-stu-id="16c28-360">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="16c28-361">また、パブリック フィールドとしてこれらの公開バニラ .NET Api の変更可能なレコードのフィールドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="16c28-361">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="16c28-362">常にクラスが API の将来の進化をより柔軟なオプションを提供するかどうかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="16c28-363">たとえば、次の F# コードは、C# コンシューマーへのパブリック API を公開します。</span><span class="sxs-lookup"><span data-stu-id="16c28-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="16c28-364">F#: </span><span class="sxs-lookup"><span data-stu-id="16c28-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="16c28-365">C#: </span><span class="sxs-lookup"><span data-stu-id="16c28-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="16c28-366">表現を非表示にF#バニラ .NET Api で共用体の型</span><span class="sxs-lookup"><span data-stu-id="16c28-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="16c28-367">F# の共用体型されません一般的に使用されるコンポーネントの境界を越えても F#-に-F# コーディングします。</span><span class="sxs-lookup"><span data-stu-id="16c28-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="16c28-368">コンポーネントとライブラリ内で内部的に使用する場合は、優れた実装デバイスです。</span><span class="sxs-lookup"><span data-stu-id="16c28-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="16c28-369">Vanilla .NET API を設計するときは、プライベート宣言または署名ファイルを使用して、union 型の表現を非表示を検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="16c28-370">提供を目的に、メンバーと共用体の表現を内部的に使用する型を追加することも可能性があります。ネットワークに接続する API です。</span><span class="sxs-lookup"><span data-stu-id="16c28-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="16c28-371">GUI を設計およびフレームワークの設計パターンを使用して他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="16c28-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="16c28-372">多くのさまざまなフレームワークは WinForms、WPF、および ASP.NET などの .NET 内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c28-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="16c28-373">これらのフレームワークで使用するためのコンポーネントをデザインする場合は、それぞれの名前付けとデザインの規則を使用してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="16c28-374">たとえば、wpf プログラミングでは、クラスを設計するための WPF 設計パターンを採用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="16c28-375">ユーザー インターフェイス プログラミング モデルの場合、イベントなどの設計パターンを使用しなどの通知ベースのコレクションにある<xref:System.Collections.ObjectModel>します。</span><span class="sxs-lookup"><span data-stu-id="16c28-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="16c28-376">(他の .NET 言語から使用するためのライブラリ) のオブジェクトとメンバーのデザイン</span><span class="sxs-lookup"><span data-stu-id="16c28-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="16c28-377">CLIEvent 属性を使用して、.NET イベントを公開するには</span><span class="sxs-lookup"><span data-stu-id="16c28-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="16c28-378">構築、`DelegateEvent`特定の .NET を使用したデリゲート オブジェクトを取得する型と`EventArgs`(なく`Event`、使用する、`FSharpHandler`既定で種類) イベントが他の .NET 言語を使い慣れた方法で公開されるため。</span><span class="sxs-lookup"><span data-stu-id="16c28-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="16c28-379">.NET のタスクを返すメソッドとしての非同期操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="16c28-379">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="16c28-380">タスクは、アクティブな非同期計算を表す .NET で使用されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="16c28-381">タスクは、一般的な F# よりも小さい合成`Async<T>`オブジェクトの場合、「は既に実行中」のタスクを表すされ、並列の合成を実行するか、キャンセルの信号、およびその他の伝達を非表示にする方法で一緒に構成することはできませんコンテキスト パラメーター。</span><span class="sxs-lookup"><span data-stu-id="16c28-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="16c28-382">ただし、この場合でもタスクを返すメソッドは .NET での非同期プログラミングの標準的な表現です。</span><span class="sxs-lookup"><span data-stu-id="16c28-382">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="16c28-383">多くの場合は、明示的なキャンセル トークンをそのまま使用することもします。</span><span class="sxs-lookup"><span data-stu-id="16c28-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="16c28-384">代わりに .NET のデリゲート型を使用して、F#関数の型</span><span class="sxs-lookup"><span data-stu-id="16c28-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="16c28-385">ここで「F# 関数型」という意味で「矢印」種類`int -> int`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-385">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="16c28-386">これには。</span><span class="sxs-lookup"><span data-stu-id="16c28-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="16c28-387">方法 :</span><span class="sxs-lookup"><span data-stu-id="16c28-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="16c28-388">として F# 関数型が表示されます`class FSharpFunc<T,U>`他の .NET 言語にはデリゲート型を理解できる言語機能とツールには適しています。</span><span class="sxs-lookup"><span data-stu-id="16c28-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="16c28-389">.NET Framework 3.5 以降を対象とする上位のメソッドを作成するときに、`System.Func`と`System.Action`デリゲートは、問題の少ない方法でこれらの Api を使用する .NET 開発者に公開する適切な Api。</span><span class="sxs-lookup"><span data-stu-id="16c28-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="16c28-390">(システム定義のデリゲート型がより限定的な .NET Framework 2.0 をターゲットにした場合など、定義済みのデリゲート型の使用を検討する必要が`System.Converter<T,U>`または特定のデリゲート型を定義します)。</span><span class="sxs-lookup"><span data-stu-id="16c28-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="16c28-391">一方で、.NET のデリゲートではない F# のライブラリに接続する (F# で、次のセクションを参照してください-ライブラリに接続する)。</span><span class="sxs-lookup"><span data-stu-id="16c28-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="16c28-392">すべて F# 関数型を使用して実装を作成し、一番上にある実際の F# シン ファサードとしてデリゲートを使用してパブリック API を作成する標準の .NET ライブラリの上位のメソッドを開発する際に一般的な実装方法は、結果として、します。実装です。</span><span class="sxs-lookup"><span data-stu-id="16c28-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="16c28-393">F# オプションの値を返す代わりに、TryGetValue パターンを使用し、引数としての F# のオプション値を取得するメソッドのオーバー ロードを優先</span><span class="sxs-lookup"><span data-stu-id="16c28-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="16c28-394">Api で F# オプションの種類の使用の一般的なパターンはより優れたバニラで実装された標準の .NET を使用した .NET Api の設計手法です。</span><span class="sxs-lookup"><span data-stu-id="16c28-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="16c28-395">返す代わりに、F#オプションの値、ブール型の戻り値の型と"TryGetValue"パターンのように out パラメーターの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="16c28-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="16c28-396">作成ではなくF#オプション パラメーターとして値をメソッドのオーバー ロードまたは省略可能な引数を使用して検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="16c28-397">使用して、.NET コレクション インターフェイス型の IEnumerable\<T\>と IDictionary\<キー, Value\>パラメーターと戻り値</span><span class="sxs-lookup"><span data-stu-id="16c28-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="16c28-398">.NET の配列などの具体的なコレクション型の使用を避けるため`T[]`、F# 型`list<T>`、`Map<Key,Value>`と`Set<T>`などの .NET の具体的なコレクション型と`Dictionary<Key,Value>`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="16c28-399">.NET ライブラリのデザイン ガイドラインがあるなどのさまざまなコレクション型を使用するタイミングに関する優れたアドバイス`IEnumerable<T>`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="16c28-400">配列のいくつかの使用 (`T[]`) は状況によっては、パフォーマンスの理由で許容されます。</span><span class="sxs-lookup"><span data-stu-id="16c28-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="16c28-401">特に注意`seq<T>`同様、F# のエイリアスは`IEnumerable<T>`、したがって seq は多くの場合、バニラ .NET API の適切な型。</span><span class="sxs-lookup"><span data-stu-id="16c28-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="16c28-402">代わりに F# の一覧です。</span><span class="sxs-lookup"><span data-stu-id="16c28-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="16c28-403">使用F#シーケンス。</span><span class="sxs-lookup"><span data-stu-id="16c28-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="16c28-404">メソッドの唯一の入力型としてユニットの種類を使用して、引数を持たないメソッドを定義またはのみとして void を返すメソッドを定義する型を返す</span><span class="sxs-lookup"><span data-stu-id="16c28-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="16c28-405">ユニットの種類の他の使用を避けてください。</span><span class="sxs-lookup"><span data-stu-id="16c28-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="16c28-406">これらは、適切です。</span><span class="sxs-lookup"><span data-stu-id="16c28-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="16c28-407">これには。</span><span class="sxs-lookup"><span data-stu-id="16c28-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="16c28-408">標準の .NET API の境界上で null 値のチェック</span><span class="sxs-lookup"><span data-stu-id="16c28-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="16c28-409">F# 実装コードに不変の設計パターンと F# の型の null リテラルの使用に関する制約のため、null の値が少ない傾向にあります。</span><span class="sxs-lookup"><span data-stu-id="16c28-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="16c28-410">他の .NET 言語多くの場合、値として null より頻繁に使用します。</span><span class="sxs-lookup"><span data-stu-id="16c28-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="16c28-411">このため、バニラ .NET API を公開する F# コードを API の境界の null のパラメーターを確認し、これらの値が F# 実装コードに深くを送信するを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="16c28-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="16c28-412">`isNull`関数またはパターンに一致する、`null`パターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="16c28-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="16c28-413">戻り値として組を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="16c28-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="16c28-414">代わりに、集計のデータを保持するか、複数の値を返す出力パラメーターを使用して名前付きの型を返すことを好みます。</span><span class="sxs-lookup"><span data-stu-id="16c28-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="16c28-415">タプルと構造体のタプルは、.NET に存在 (c# の構造体のタプルの言語サポートを含む)、最もよくが用意されて、理想的なと予想される API .NET 開発者向け。</span><span class="sxs-lookup"><span data-stu-id="16c28-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="16c28-416">パラメーターのカリー化を使用をしません。</span><span class="sxs-lookup"><span data-stu-id="16c28-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="16c28-417">代わりに、.NET の呼び出し規約を使用して、`Method(arg1,arg2,…,argN)`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="16c28-418">ヒント :任意の .NET 言語から使用するためのライブラリを設計するかどうかは、実験の一部が実際に行ってものはありませんC#および Visual Basic のプログラミング ライブラリ「フィール右」これらの言語からことを確認します。</span><span class="sxs-lookup"><span data-stu-id="16c28-418">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="16c28-419">ライブラリとそのドキュメントが開発者に期待どおりに表示されていることを確認するのに、.NET Reflector Visual Studio オブジェクト ブラウザーなどのツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="16c28-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="16c28-420">付録</span><span class="sxs-lookup"><span data-stu-id="16c28-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="16c28-421">他の .NET 言語で使用するために F# コードの設計のエンド ツー エンドの例</span><span class="sxs-lookup"><span data-stu-id="16c28-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="16c28-422">次のクラスを検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c28-422">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="16c28-423">このクラスの推定の F# 型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16c28-423">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="16c28-424">この F# 型が別の .NET 言語を使用してプログラマに表示する方法を見てをみましょう。</span><span class="sxs-lookup"><span data-stu-id="16c28-424">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="16c28-425">たとえば、おおよそ C#「署名」とおりです。</span><span class="sxs-lookup"><span data-stu-id="16c28-425">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="16c28-426">方法について注意する重要な点があるF#表しますをここで構築します。</span><span class="sxs-lookup"><span data-stu-id="16c28-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="16c28-427">例:</span><span class="sxs-lookup"><span data-stu-id="16c28-427">For example:</span></span>

* <span data-ttu-id="16c28-428">引数名などのメタデータが保持されています。</span><span class="sxs-lookup"><span data-stu-id="16c28-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="16c28-429">2 つの引数を取る F# メソッドでは、2 つの引数を取る C# メソッドになります。</span><span class="sxs-lookup"><span data-stu-id="16c28-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="16c28-430">関数とリストは、対応する型が F# ライブラリへの参照になります。</span><span class="sxs-lookup"><span data-stu-id="16c28-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="16c28-431">次のコードでは、このコードは、これらの点を考慮に入れてを調整する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="16c28-431">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="16c28-432">コードの推定の F# 型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16c28-432">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="16c28-433">C# シグネチャは次のように、ようになりました。</span><span class="sxs-lookup"><span data-stu-id="16c28-433">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="16c28-434">Vanilla .NET ライブラリの一部は次のように、この型を使用する準備を修正します。</span><span class="sxs-lookup"><span data-stu-id="16c28-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="16c28-435">いくつかの名前を調整: `Point1`、 `n`、 `l`、および`f`になった`RadialPoint`、 `count`、 `factor`、および`transform`、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="16c28-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="16c28-436">戻り値の型を使用する`seq<RadialPoint>`の代わりに`RadialPoint list`を使用してリストの構築を変更することで`[ ... ]`を使用してシーケンスの構築に`IEnumerable<RadialPoint>`します。</span><span class="sxs-lookup"><span data-stu-id="16c28-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="16c28-437">.NET のデリゲート型を使用する`System.Func`F# 関数型の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="16c28-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="16c28-438">これにより、c# コードで使用するよりはるかにします。</span><span class="sxs-lookup"><span data-stu-id="16c28-438">This makes it far nicer to consume in C# code.</span></span>
