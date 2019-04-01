---
title: /refout (C# コンパイラ オプション)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 06d21843c6e2d7aeb1858c3ce72426d080f73595
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410213"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="fbc6a-102">/refout (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="fbc6a-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="fbc6a-103">**-refout** オプションは、参照アセンブリを出力するファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="fbc6a-104">Emit API では、これを `metadataPeStream` に変換します。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-104">This translates to `metadataPeStream` in the Emit API.</span></span>

## <a name="syntax"></a><span data-ttu-id="fbc6a-105">構文</span><span class="sxs-lookup"><span data-stu-id="fbc6a-105">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="fbc6a-106">引数</span><span class="sxs-lookup"><span data-stu-id="fbc6a-106">Arguments</span></span>

 <span data-ttu-id="fbc6a-107">`filepath` 参照アセンブリのファイル パス。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-107">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="fbc6a-108">通常はプライマリ アセンブリのファイルパスと一致します。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-108">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="fbc6a-109">(MSBuild で使用される) 推奨規則は、プライマリ アセンブリに相対する "ref/" サブ フォルダー内に参照アセンブリを配置することです。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="fbc6a-110">解説</span><span class="sxs-lookup"><span data-stu-id="fbc6a-110">Remarks</span></span>

<span data-ttu-id="fbc6a-111">メタデータのみアセンブリには、1 つの `throw null` 本体で置き換えられたメソッド本体がありますが、匿名型を除くすべてのメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-111">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="fbc6a-112">(本体なしではなく) `throw null` 本体を使用する理由は、PEVerify を実行して渡せるようにするためです (そのためにメタデータの完全性を検証します)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-112">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="fbc6a-113">参照アセンブリには、アセンブリ レベルの `ReferenceAssembly` 属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-113">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="fbc6a-114">この属性は、ソースで指定できます (指定すると、コンパイラではこれを合成する必要がなくなります)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-114">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="fbc6a-115">この属性により、ランタイムで実行のための参照アセンブリの読み込みが拒否されます (ただし、リフレクションのみモードでは読み込むことができます)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-115">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="fbc6a-116">アセンブリにリフレクションするツールでは、参照アセンブリをリフレクションのみで読み込んでいることを確認する必要があります。そうでない場合、ランタイムから typeload エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-116">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="fbc6a-117">参照アセンブリは、メタデータのみアセンブリからさらにメタデータ (プライベート メンバー) を削除します。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-117">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="fbc6a-118">参照アセンブリには、API サーフェスでそれが必要とする参照のみがあります。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-118">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="fbc6a-119">実際のアセンブリには、特定の実装に関連するその他の参照がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-119">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="fbc6a-120">たとえば、`class C { private void M() { dynamic d = 1; ... } }` の参照アセンブリは、`dynamic` に必要などの型も参照しません。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-120">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="fbc6a-121">プライベート関数のメンバー (メソッド、プロパティ、およびイベント) は、それらの削除がコンパイルに著しい影響を与えない場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-121">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="fbc6a-122"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性がない場合、内部関数メンバーに同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-122">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="fbc6a-123">ただし、すべての型 (プライベートまたは入れ子になった型を含む) は参照アセンブリで保持されます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-123">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="fbc6a-124">すべての属性が (内部属性も) 保持されます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-124">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="fbc6a-125">すべての仮想メソッドが保持されます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-125">All virtual methods are kept.</span></span> <span data-ttu-id="fbc6a-126">明示的なインターフェイスの実装が保持されます。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-126">Explicit interface implementations are kept.</span></span> <span data-ttu-id="fbc6a-127">明示的に実装されたプロパティとイベントが保持されます (これらのアクセサーが仮想のため保持されます)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-127">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="fbc6a-128">構造体のすべてのフィールドが保持されます </span><span class="sxs-lookup"><span data-stu-id="fbc6a-128">All fields of a struct are kept.</span></span> <span data-ttu-id="fbc6a-129">(これは、post-C#-7.1 絞り込みの候補です)。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-129">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="fbc6a-130">`-refout` オプションと [`-refonly`](refonly-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="fbc6a-130">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbc6a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbc6a-131">See also</span></span>

- [<span data-ttu-id="fbc6a-132">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="fbc6a-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="fbc6a-133">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="fbc6a-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
