---
title: /refout (C# コンパイラ オプション)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 97cbf540527d0449387b71bb1d97df95b6a4aba4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602504"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="bf93e-102">/refout (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="bf93e-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="bf93e-103">**-refout** オプションは、参照アセンブリを出力するファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf93e-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="bf93e-104">Emit API では、これを `metadataPeStream` に変換します。</span><span class="sxs-lookup"><span data-stu-id="bf93e-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="bf93e-105">このオプションは、MSBuild の [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) プロジェクト プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="bf93e-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf93e-106">構文</span><span class="sxs-lookup"><span data-stu-id="bf93e-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="bf93e-107">引数</span><span class="sxs-lookup"><span data-stu-id="bf93e-107">Arguments</span></span>

 <span data-ttu-id="bf93e-108">`filepath` 参照アセンブリのファイル パス。</span><span class="sxs-lookup"><span data-stu-id="bf93e-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="bf93e-109">通常はプライマリ アセンブリのファイルパスと一致します。</span><span class="sxs-lookup"><span data-stu-id="bf93e-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="bf93e-110">(MSBuild で使用される) 推奨規則は、プライマリ アセンブリに相対する "ref/" サブ フォルダー内に参照アセンブリを配置することです。</span><span class="sxs-lookup"><span data-stu-id="bf93e-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf93e-111">解説</span><span class="sxs-lookup"><span data-stu-id="bf93e-111">Remarks</span></span>

<span data-ttu-id="bf93e-112">メタデータのみアセンブリには、1 つの `throw null` 本体で置き換えられたメソッド本体がありますが、匿名型を除くすべてのメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-112">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="bf93e-113">(本体なしではなく) `throw null` 本体を使用する理由は、PEVerify を実行して渡せるようにするためです (そのためにメタデータの完全性を検証します)。</span><span class="sxs-lookup"><span data-stu-id="bf93e-113">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="bf93e-114">参照アセンブリには、アセンブリ レベルの `ReferenceAssembly` 属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-114">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="bf93e-115">この属性は、ソースで指定できます (指定すると、コンパイラではこれを合成する必要がなくなります)。</span><span class="sxs-lookup"><span data-stu-id="bf93e-115">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="bf93e-116">この属性により、ランタイムで実行のための参照アセンブリの読み込みが拒否されます (ただし、リフレクションのみモードでは読み込むことができます)。</span><span class="sxs-lookup"><span data-stu-id="bf93e-116">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="bf93e-117">アセンブリにリフレクションするツールでは、参照アセンブリをリフレクションのみで読み込んでいることを確認する必要があります。そうでない場合、ランタイムから typeload エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bf93e-117">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="bf93e-118">参照アセンブリは、メタデータのみアセンブリからさらにメタデータ (プライベート メンバー) を削除します。</span><span class="sxs-lookup"><span data-stu-id="bf93e-118">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="bf93e-119">参照アセンブリには、API サーフェスでそれが必要とする参照のみがあります。</span><span class="sxs-lookup"><span data-stu-id="bf93e-119">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="bf93e-120">実際のアセンブリには、特定の実装に関連するその他の参照がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf93e-120">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="bf93e-121">たとえば、`class C { private void M() { dynamic d = 1; ... } }` の参照アセンブリは、`dynamic` に必要などの型も参照しません。</span><span class="sxs-lookup"><span data-stu-id="bf93e-121">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="bf93e-122">プライベート関数のメンバー (メソッド、プロパティ、およびイベント) は、それらの削除がコンパイルに著しい影響を与えない場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-122">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="bf93e-123"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性がない場合、内部関数メンバーに同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="bf93e-123">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="bf93e-124">ただし、すべての型 (プライベートまたは入れ子になった型を含む) は参照アセンブリで保持されます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-124">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="bf93e-125">すべての属性が (内部属性も) 保持されます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-125">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="bf93e-126">すべての仮想メソッドが保持されます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-126">All virtual methods are kept.</span></span> <span data-ttu-id="bf93e-127">明示的なインターフェイスの実装が保持されます。</span><span class="sxs-lookup"><span data-stu-id="bf93e-127">Explicit interface implementations are kept.</span></span> <span data-ttu-id="bf93e-128">明示的に実装されたプロパティとイベントが保持されます (これらのアクセサーが仮想のため保持されます)。</span><span class="sxs-lookup"><span data-stu-id="bf93e-128">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="bf93e-129">構造体のすべてのフィールドが保持されます</span><span class="sxs-lookup"><span data-stu-id="bf93e-129">All fields of a struct are kept.</span></span> <span data-ttu-id="bf93e-130">(これは、post-C#-7.1 絞り込みの候補です)。</span><span class="sxs-lookup"><span data-stu-id="bf93e-130">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="bf93e-131">`-refout` オプションと [`-refonly`](refonly-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="bf93e-131">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf93e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf93e-132">See also</span></span>

- [<span data-ttu-id="bf93e-133">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="bf93e-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="bf93e-134">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="bf93e-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
