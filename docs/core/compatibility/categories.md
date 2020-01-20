---
title: 破壊的変更のカテゴリ - .NET Core
description: .NET Core での破壊的変更のカテゴリの分類方法について説明します。
ms.date: 06/10/2019
ms.openlocfilehash: 32cf55dc3ba0b16bae8cfe6179211150b2c90e2c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343596"
---
# <a name="breaking-change-categories"></a><span data-ttu-id="3a3d0-103">破壊的変更のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="3a3d0-103">Breaking change categories</span></span>

<span data-ttu-id="3a3d0-104">"*互換性*" とは、コードが最初に開発されたときのものとは異なる .NET 実装のバージョンで、コードがコンパイルまたは実行できることを指します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-104">*Compatibility* refers to the ability to compile or execute code on a version of a .NET implementation other than the one with which the code was originally developed.</span></span> <span data-ttu-id="3a3d0-105">特定の変更があると、6 つの異なる方法で互換性に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-105">A particular change can affect compatibility in six different ways.</span></span> <span data-ttu-id="3a3d0-106">互換性を評価するときに考慮される[変更の個々の種類](index.md)は、次の 5 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-106">The [individual kinds of changes](index.md) that are considered when evaluating compatibility fall into the following categories:</span></span>

- [<span data-ttu-id="3a3d0-107">動作の変更</span><span class="sxs-lookup"><span data-stu-id="3a3d0-107">behavioral change</span></span>](#behavioral-change)
- [<span data-ttu-id="3a3d0-108">バイナリの互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-108">binary compatibility</span></span>](#binary-compatibility)
- [<span data-ttu-id="3a3d0-109">ソースの互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-109">source compatibility</span></span>](#source-compatibility)
- [<span data-ttu-id="3a3d0-110">デザイン時の互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-110">design-time compatibility</span></span>](#design-time-compatibility)
- [<span data-ttu-id="3a3d0-111">下位互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-111">backwards compatibility</span></span>](#backwards-compatibility)
- <span data-ttu-id="3a3d0-112">[上位互換性](#forward-compatibility) (.NET Core の目標ではありません)</span><span class="sxs-lookup"><span data-stu-id="3a3d0-112">[forward compatibility](#forward-compatibility) (not a goal of .NET Core)</span></span>

## <a name="behavioral-change"></a><span data-ttu-id="3a3d0-113">動作の変更</span><span class="sxs-lookup"><span data-stu-id="3a3d0-113">Behavioral change</span></span>

<span data-ttu-id="3a3d0-114">動作の変更とは、メンバーの動作の変更を指します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-114">A behavioral change represents a change to the behavior of a member.</span></span> <span data-ttu-id="3a3d0-115">この変更は、外部から参照可能 (たとえば、メソッドが別の例外をスローするなど) である場合があります。または、変更された実装 (たとえば、戻り値の計算方法の変更、メソッドの内部呼び出しの追加または削除、またはパフォーマンスの大幅な向上など) を指す場合があります。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-115">The change may be externally visible (for example, a method may throw a different exception), or it may represent a changed implementation (for example, a change in the way a return value is calculated, the addition or removal of internal method calls, or even a significant performance improvement).</span></span>

<span data-ttu-id="3a3d0-116">動作の変更が、外部から参照可能、かつ型のパブリック コントラクトを変更するものである場合、バイナリの互換性に影響するため、簡単に評価できます。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-116">When behavioral changes are externally visible and modify a type's public contract, they are easy to evaluate since they affect binary compatibility.</span></span> <span data-ttu-id="3a3d0-117">実装の変更の評価はさらに困難です。変更の性質、および API の使用の頻度およびパターンによって、変更の影響は深刻なものから無害なものにまで及びます。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-117">Implementation changes are much more difficult to evaluate; depending on the nature of the change and the frequency and patterns of use of the API, the impact of a change can range from severe to innocuous.</span></span>

## <a name="binary-compatibility"></a><span data-ttu-id="3a3d0-118">バイナリの互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-118">Binary compatibility</span></span>

<span data-ttu-id="3a3d0-119">バイナリの互換性とは、API のコンシューマーが、再コンパイルせずに新しいバージョンで API を使用できることです。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-119">Binary compatibility refers to the ability of a consumer of an API to use the API on a newer version without recompilation.</span></span> <span data-ttu-id="3a3d0-120">型へのメソッドの追加または新しいインターフェイス実装の追加などの変更は、バイナリの互換性には影響しません。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-120">Such changes as adding methods or adding a new interface implementation to a type do not affect binary compatibility.</span></span> <span data-ttu-id="3a3d0-121">しかし、アセンブリによって公開されるインターフェイスと同じものにコンシューマーがアクセスできなくなるように、アセンブリのパブリック シグネチャが削除または変更されると、バイナリの互換性が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-121">However, removing or altering an assembly's public signatures so that consumers can no longer access the same interface exposed by the assembly does affect binary compatibility.</span></span> <span data-ttu-id="3a3d0-122">このような種類の変更は、"*バイナリ非互換な変更*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-122">A change of this kind is termed a *binary incompatible change*.</span></span>

## <a name="source-compatibility"></a><span data-ttu-id="3a3d0-123">ソースの互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-123">Source compatibility</span></span>

<span data-ttu-id="3a3d0-124">ソースの互換性とは、API の既存のコンシューマーが、ソースを変更せずに新しいバージョンに再コンパイルできることを指します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-124">Source compatibility refers to the ability of existing consumers of an API to recompile against a newer version without any source changes.</span></span> <span data-ttu-id="3a3d0-125">"*ソース非互換な変更*" は、コンシューマーが新しいバージョンの API が正しくビルドされるように、ソース コードを変更する必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-125">A *source incompatible change* occurs when a consumer needs to modify source code for it to build successfully against a newer version of an API.</span></span>

## <a name="design-time-compatibility"></a><span data-ttu-id="3a3d0-126">デザイン時の互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-126">Design-time compatibility</span></span>

<span data-ttu-id="3a3d0-127">デザイン時の互換性とは、デザイン時のエクスペリエンスを Visual Studio の複数のバージョン間およびその他のデザイン時環境で維持できることを指します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-127">Design-time compatibility refers to preserving the design-time experience across versions of Visual Studio and other design-time environments.</span></span> <span data-ttu-id="3a3d0-128">デザイン時の互換性には、デザイナーの動作または UI も含まれる場合がありますが、プロジェクトの互換性が最も重要です。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-128">While this can involve the behavior or the UI of designers, the most important aspect of design-time compatibility concerns project compatibility.</span></span> <span data-ttu-id="3a3d0-129">プロジェクトまたはソリューションは、そのデザイン時環境の新しいバージョンで開いて使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-129">A project or solution must be able to be opened and used on a newer version of the design-time environment.</span></span>

## <a name="backwards-compatibility"></a><span data-ttu-id="3a3d0-130">下位互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-130">Backwards compatibility</span></span>

<span data-ttu-id="3a3d0-131">下位互換性とは、API の既存のコンシューマーが、新しいバージョンに対して同じ動作で実行できることを指します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-131">Backwards compatibility refers to the ability of an existing consumer of an API to run against a new version while behaving in the same way.</span></span> <span data-ttu-id="3a3d0-132">動作の変更とバイナリの互換性の変更の両方が、下位互換性に影響します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-132">Both behavioral changes and changes in binary compatibility affect backwards compatibility.</span></span> <span data-ttu-id="3a3d0-133">コンシューマーがその API の新しいバージョンで実行されるときに、実行できない、または動作が異なる場合、その API は "*下位非互換*" です。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-133">If a consumer is not able to run or behaves differently when running against the newer version of the API, the API is *backwards incompatible*.</span></span>

<span data-ttu-id="3a3d0-134">開発者は新しいバージョンの API が下位互換であることを期待しているので、下位互換性に影響する変更は行わないことを推奨します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-134">Changes that affect backwards compatibility are discouraged, since developers expect backwards compatibility in newer versions of an API.</span></span>

## <a name="forward-compatibility"></a><span data-ttu-id="3a3d0-135">上位互換性</span><span class="sxs-lookup"><span data-stu-id="3a3d0-135">Forward compatibility</span></span>

<span data-ttu-id="3a3d0-136">上位互換性とは、API の既存のコンシューマーが、古いバージョンに対して同じ動作を示して実行できることを指します。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-136">Forward compatibility refers to the ability of an existing consumer of an API to run against an older version while exhibiting the same behavior.</span></span> <span data-ttu-id="3a3d0-137">コンシューマーがその API の新しいバージョンで実行されるときに、実行できない、または動作が異なる場合、その API は "*上位非互換*" です。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-137">If a consumer is not able to run or behaves differently when run against an older version of the API, the API is *forward incompatible*.</span></span>

<span data-ttu-id="3a3d0-138">上位互換を維持するということは、バージョン間でどのような変更や追加も実質的に行わないことを意味します。より新しいバージョンを対象とするコンシューマーが以前のバージョンで実行されるのを、これらの変更が阻止するためです。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-138">Maintaining forward compatibility virtually precludes any changes or additions from version to version, since those changes prevent a consumer that targets a later version from running under an earlier version.</span></span> <span data-ttu-id="3a3d0-139">開発者は、より新しい API に依存するコンシューマーが古い API では正しく動作しない場合があると想定しています。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-139">Developers expect that a consumer that relies on a newer API may not function correctly against the older API.</span></span>

<span data-ttu-id="3a3d0-140">上位互換性の維持が .NET Core の目標ではないのです。</span><span class="sxs-lookup"><span data-stu-id="3a3d0-140">Maintaining forward compatibility is not a goal of .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a3d0-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a3d0-141">See also</span></span>

- [<span data-ttu-id="3a3d0-142">.NET Core の破壊的変更を評価する</span><span class="sxs-lookup"><span data-stu-id="3a3d0-142">Evaluate breaking changes in .NET Core</span></span>](index.md)
