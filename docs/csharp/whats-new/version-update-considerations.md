---
title: C# 開発者向けのバージョンと更新に関する考慮事項
description: 新しい言語機能をライブラリに導入すると、それを使用するコードに影響が出る可能性があります。
ms.date: 09/19/2018
ms.openlocfilehash: 3ffe2f6fd64a391fddf28233dccb022c95851884
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634487"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="1af1f-103">C# 開発者向けのバージョンと更新に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1af1f-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="1af1f-104">互換性は、新しい機能を C# 言語に追加するときの非常に重要な目標です。</span><span class="sxs-lookup"><span data-stu-id="1af1f-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="1af1f-105">ほとんどの場合、既存のコードは、新しいコンパイラのバージョンで問題なく再コンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="1af1f-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="1af1f-106">新しい言語機能をライブラリに導入するときに、配慮が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1af1f-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="1af1f-107">最新バージョンで見つかった機能を使用して新しいライブラリを作成したが、コンパイラの以前のバージョンを使用してビルドされたアプリがそれを使用できることを保証しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1af1f-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="1af1f-108">または、既存のライブラリをアップグレードしたが、多くのユーザーがバージョンをまだアップグレードしていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1af1f-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="1af1f-109">新しい機能の導入を検討するときは、互換性の 2 つのバリエーション (ソース互換とバイナリ互換) を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1af1f-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="1af1f-110">バイナリ互換の変更</span><span class="sxs-lookup"><span data-stu-id="1af1f-110">Binary compatible changes</span></span>

<span data-ttu-id="1af1f-111">更新されたライブラリを、アプリケーションとそれを使用するライブラリのリビルドなしで使用できる場合、ライブラリの変更は**バイナリ互換**です。</span><span class="sxs-lookup"><span data-stu-id="1af1f-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="1af1f-112">依存するアセンブリのリビルドも、ソース コードの変更も必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1af1f-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="1af1f-113">バイナリ互換の変更は、ソース互換の変更でもあります。</span><span class="sxs-lookup"><span data-stu-id="1af1f-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="1af1f-114">ソース互換の変更</span><span class="sxs-lookup"><span data-stu-id="1af1f-114">Source compatible changes</span></span>

<span data-ttu-id="1af1f-115">更新されたライブラリを使用するアプリケーションとライブラリではソース コードの変更を必要としませんが、ソースを正常に動作させるには、新しいバージョンで再コンパイルする必要がある場合、ライブラリの変更は**ソース互換**です。</span><span class="sxs-lookup"><span data-stu-id="1af1f-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="1af1f-116">互換性のない変更</span><span class="sxs-lookup"><span data-stu-id="1af1f-116">Incompatible changes</span></span>

<span data-ttu-id="1af1f-117">変更が**ソース互換**と**バイナリ互換**のどちらでもない場合は、依存するライブラリとアプリケーションのソース コードの変更と再コンパイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="1af1f-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="1af1f-118">ライブラリを評価する</span><span class="sxs-lookup"><span data-stu-id="1af1f-118">Evaluate your library</span></span>

<span data-ttu-id="1af1f-119">これらの互換性の概念は、ライブラリの内部実装ではなく、public 宣言と protected 宣言に影響します。</span><span class="sxs-lookup"><span data-stu-id="1af1f-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="1af1f-120">新しい機能の内部的な導入は、常に**バイナリ互換**です。</span><span class="sxs-lookup"><span data-stu-id="1af1f-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="1af1f-121">**バイナリ互換**の変更では、古い構文の public 宣言と同じコンパイル済みコードを生成する新しい構文があります。</span><span class="sxs-lookup"><span data-stu-id="1af1f-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="1af1f-122">たとえば、メソッドを式形式のメンバーに変更することは、**バイナリ互換の変更**です。</span><span class="sxs-lookup"><span data-stu-id="1af1f-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="1af1f-123">元のコード:</span><span class="sxs-lookup"><span data-stu-id="1af1f-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="1af1f-124">新しいコード:</span><span class="sxs-lookup"><span data-stu-id="1af1f-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="1af1f-125">**ソース互換**の変更では、public メンバーのコンパイル コードを変更する構文が導入されますが、それは既存の呼び出しサイトと互換性がある方法で行われます。</span><span class="sxs-lookup"><span data-stu-id="1af1f-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="1af1f-126">たとえば、メソッドのシグネチャを値によるパラメーターから `in` 参照によるパラメーターに変更することはソース互換ですが、バイナリ互換ではありません。</span><span class="sxs-lookup"><span data-stu-id="1af1f-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="1af1f-127">元のコード:</span><span class="sxs-lookup"><span data-stu-id="1af1f-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="1af1f-128">新しいコード:</span><span class="sxs-lookup"><span data-stu-id="1af1f-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="1af1f-129">[新機能](index.md)に関する記事に、public 宣言に影響する機能の導入がソース互換であるかバイナリ互換であるかについての注が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1af1f-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>
