---
title: -refonly (C# コンパイラ オプション)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: eb62f98c5d548fe3583d3422eb7b6020a82c296a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606486"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="6214b-102">-refonly (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="6214b-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="6214b-103">**-refonly** オプションは、実装アセンブリではなく、参照アセンブリをプライマリ出力として出力することを示します。</span><span class="sxs-lookup"><span data-stu-id="6214b-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="6214b-104">`-refonly` パラメーターは、参照アセンブリを実行できない場合に、PDB の出力を暗黙的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="6214b-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="6214b-105">このオプションは、MSBuild の [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) プロジェクト プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="6214b-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="6214b-106">構文</span><span class="sxs-lookup"><span data-stu-id="6214b-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="6214b-107">解説</span><span class="sxs-lookup"><span data-stu-id="6214b-107">Remarks</span></span>

<span data-ttu-id="6214b-108">メタデータのみアセンブリには、1 つの `throw null` 本体で置き換えられたメソッド本体がありますが、匿名型を除くすべてのメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6214b-108">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="6214b-109">(本体なしではなく) `throw null` 本体を使用する理由は、PEVerify を実行して渡せるようにするためです (そのためにメタデータの完全性を検証します)。</span><span class="sxs-lookup"><span data-stu-id="6214b-109">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="6214b-110">参照アセンブリには、アセンブリ レベルの `ReferenceAssembly` 属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6214b-110">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="6214b-111">この属性は、ソースで指定できます (指定すると、コンパイラではこれを合成する必要がなくなります)。</span><span class="sxs-lookup"><span data-stu-id="6214b-111">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="6214b-112">この属性により、ランタイムで実行のための参照アセンブリの読み込みが拒否されます (ただし、リフレクションのみモードでは読み込むことができます)。</span><span class="sxs-lookup"><span data-stu-id="6214b-112">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="6214b-113">アセンブリにリフレクションするツールでは、参照アセンブリをリフレクションのみで読み込んでいることを確認する必要があります。そうでない場合、ランタイムから typeload エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6214b-113">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="6214b-114">参照アセンブリは、メタデータのみアセンブリからさらにメタデータ (プライベート メンバー) を削除します。</span><span class="sxs-lookup"><span data-stu-id="6214b-114">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="6214b-115">参照アセンブリには、API サーフェスでそれが必要とする参照のみがあります。</span><span class="sxs-lookup"><span data-stu-id="6214b-115">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="6214b-116">実際のアセンブリには、特定の実装に関連するその他の参照がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6214b-116">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="6214b-117">たとえば、`class C { private void M() { dynamic d = 1; ... } }` の参照アセンブリは、`dynamic` に必要などの型も参照しません。</span><span class="sxs-lookup"><span data-stu-id="6214b-117">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="6214b-118">プライベート関数のメンバー (メソッド、プロパティ、およびイベント) は、それらの削除がコンパイルに著しい影響を与えない場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="6214b-118">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="6214b-119"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性がない場合、内部関数メンバーに同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="6214b-119">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="6214b-120">ただし、すべての型 (プライベートまたは入れ子になった型を含む) は参照アセンブリで保持されます。</span><span class="sxs-lookup"><span data-stu-id="6214b-120">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="6214b-121">すべての属性が (内部属性も) 保持されます。</span><span class="sxs-lookup"><span data-stu-id="6214b-121">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="6214b-122">すべての仮想メソッドが保持されます。</span><span class="sxs-lookup"><span data-stu-id="6214b-122">All virtual methods are kept.</span></span> <span data-ttu-id="6214b-123">明示的なインターフェイスの実装が保持されます。</span><span class="sxs-lookup"><span data-stu-id="6214b-123">Explicit interface implementations are kept.</span></span> <span data-ttu-id="6214b-124">明示的に実装されたプロパティとイベントが保持されます (これらのアクセサーが仮想のため保持されます)。</span><span class="sxs-lookup"><span data-stu-id="6214b-124">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="6214b-125">構造体のすべてのフィールドが保持されます</span><span class="sxs-lookup"><span data-stu-id="6214b-125">All fields of a struct are kept.</span></span> <span data-ttu-id="6214b-126">(これは、post-C#-7.1 絞り込みの候補です)。</span><span class="sxs-lookup"><span data-stu-id="6214b-126">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="6214b-127">`-refonly` オプションと [`-refout`](refout-compiler-option.md) オプションは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="6214b-127">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="6214b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6214b-128">See also</span></span>

- [<span data-ttu-id="6214b-129">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="6214b-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6214b-130">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="6214b-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
