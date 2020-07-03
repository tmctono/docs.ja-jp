---
title: 互換性
description: コードの変更が .NET の互換性に影響を与えるしくみについて説明します。
ms.date: 06/10/2019
ms.openlocfilehash: 1cf14b7ff4143367653bd1c305cc1dda6711f980
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415694"
---
# <a name="how-code-changes-can-affect-compatibility"></a><span data-ttu-id="6d673-103">コード変更が互換性に影響を与えるしくみ</span><span class="sxs-lookup"><span data-stu-id="6d673-103">How code changes can affect compatibility</span></span>

<span data-ttu-id="6d673-104">"*互換性*" とは、コードが最初に開発されたときのものとは異なる .NET 実装のバージョンで、コードがコンパイルまたは実行できることを指します。</span><span class="sxs-lookup"><span data-stu-id="6d673-104">*Compatibility* refers to the ability to compile or execute code on a version of a .NET implementation other than the one with which the code was originally developed.</span></span> <span data-ttu-id="6d673-105">[特定の変更](index.md)があると、6 つの異なる方法で互換性に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d673-105">A [particular change](index.md) can affect compatibility in six different ways:</span></span>

- [<span data-ttu-id="6d673-106">動作の変更</span><span class="sxs-lookup"><span data-stu-id="6d673-106">Behavioral change</span></span>](#behavioral-change)
- [<span data-ttu-id="6d673-107">バイナリの互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-107">Binary compatibility</span></span>](#binary-compatibility)
- [<span data-ttu-id="6d673-108">ソースの互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-108">Source compatibility</span></span>](#source-compatibility)
- [<span data-ttu-id="6d673-109">デザイン時の互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-109">Design-time compatibility</span></span>](#design-time-compatibility)
- [<span data-ttu-id="6d673-110">下位互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-110">Backwards compatibility</span></span>](#backwards-compatibility)
- <span data-ttu-id="6d673-111">[上位互換性](#forward-compatibility) (.NET Core の目標ではありません)</span><span class="sxs-lookup"><span data-stu-id="6d673-111">[Forward compatibility](#forward-compatibility) (not a goal of .NET Core)</span></span>

## <a name="behavioral-change"></a><span data-ttu-id="6d673-112">動作の変更</span><span class="sxs-lookup"><span data-stu-id="6d673-112">Behavioral change</span></span>

<span data-ttu-id="6d673-113">動作の変更とは、メンバーの動作の変更を指します。</span><span class="sxs-lookup"><span data-stu-id="6d673-113">A behavioral change represents a change to the behavior of a member.</span></span> <span data-ttu-id="6d673-114">この変更は、外部から参照可能 (たとえば、メソッドが別の例外をスローするなど) である場合があります。または、変更された実装 (たとえば、戻り値の計算方法の変更、メソッドの内部呼び出しの追加または削除、またはパフォーマンスの大幅な向上など) を指す場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d673-114">The change may be externally visible (for example, a method may throw a different exception), or it may represent a changed implementation (for example, a change in the way a return value is calculated, the addition or removal of internal method calls, or even a significant performance improvement).</span></span>

<span data-ttu-id="6d673-115">動作の変更が、外部から参照可能、かつ型のパブリック コントラクトを変更するものである場合、バイナリの互換性に影響するため、簡単に評価できます。</span><span class="sxs-lookup"><span data-stu-id="6d673-115">When behavioral changes are externally visible and modify a type's public contract, they are easy to evaluate since they affect binary compatibility.</span></span> <span data-ttu-id="6d673-116">実装の変更の評価はさらに困難です。変更の性質、および API の使用の頻度およびパターンによって、変更の影響は深刻なものから無害なものにまで及びます。</span><span class="sxs-lookup"><span data-stu-id="6d673-116">Implementation changes are much more difficult to evaluate; depending on the nature of the change and the frequency and patterns of use of the API, the impact of a change can range from severe to innocuous.</span></span>

## <a name="binary-compatibility"></a><span data-ttu-id="6d673-117">バイナリの互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-117">Binary compatibility</span></span>

<span data-ttu-id="6d673-118">バイナリの互換性とは、API のコンシューマーが、再コンパイルせずに新しいバージョンで API を使用できることです。</span><span class="sxs-lookup"><span data-stu-id="6d673-118">Binary compatibility refers to the ability of a consumer of an API to use the API on a newer version without recompilation.</span></span> <span data-ttu-id="6d673-119">型へのメソッドの追加または新しいインターフェイス実装の追加などの変更は、バイナリの互換性には影響しません。</span><span class="sxs-lookup"><span data-stu-id="6d673-119">Such changes as adding methods or adding a new interface implementation to a type do not affect binary compatibility.</span></span> <span data-ttu-id="6d673-120">しかし、アセンブリによって公開されるインターフェイスと同じものにコンシューマーがアクセスできなくなるように、アセンブリのパブリック シグネチャが削除または変更されると、バイナリの互換性が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="6d673-120">However, removing or altering an assembly's public signatures so that consumers can no longer access the same interface exposed by the assembly does affect binary compatibility.</span></span> <span data-ttu-id="6d673-121">このような種類の変更は、"*バイナリ非互換な変更*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6d673-121">A change of this kind is termed a *binary incompatible change*.</span></span>

## <a name="source-compatibility"></a><span data-ttu-id="6d673-122">ソースの互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-122">Source compatibility</span></span>

<span data-ttu-id="6d673-123">ソースの互換性とは、API の既存のコンシューマーが、ソースを変更せずに新しいバージョンに再コンパイルできることを指します。</span><span class="sxs-lookup"><span data-stu-id="6d673-123">Source compatibility refers to the ability of existing consumers of an API to recompile against a newer version without any source changes.</span></span> <span data-ttu-id="6d673-124">"*ソース非互換な変更*" は、コンシューマーが新しいバージョンの API が正しくビルドされるように、ソース コードを変更する必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6d673-124">A *source incompatible change* occurs when a consumer needs to modify source code for it to build successfully against a newer version of an API.</span></span>

## <a name="design-time-compatibility"></a><span data-ttu-id="6d673-125">デザイン時の互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-125">Design-time compatibility</span></span>

<span data-ttu-id="6d673-126">デザイン時の互換性とは、デザイン時のエクスペリエンスを Visual Studio の複数のバージョン間およびその他のデザイン時環境で維持できることを指します。</span><span class="sxs-lookup"><span data-stu-id="6d673-126">Design-time compatibility refers to preserving the design-time experience across versions of Visual Studio and other design-time environments.</span></span> <span data-ttu-id="6d673-127">デザイン時の互換性には、デザイナーの動作または UI も含まれる場合がありますが、プロジェクトの互換性が最も重要です。</span><span class="sxs-lookup"><span data-stu-id="6d673-127">While this can involve the behavior or the UI of designers, the most important aspect of design-time compatibility concerns project compatibility.</span></span> <span data-ttu-id="6d673-128">プロジェクトまたはソリューションは、そのデザイン時環境の新しいバージョンで開いて使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d673-128">A project or solution must be able to be opened and used on a newer version of the design-time environment.</span></span>

## <a name="backwards-compatibility"></a><span data-ttu-id="6d673-129">下位互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-129">Backwards compatibility</span></span>

<span data-ttu-id="6d673-130">下位互換性とは、API の既存のコンシューマーが、新しいバージョンに対して同じ動作で実行できることを指します。</span><span class="sxs-lookup"><span data-stu-id="6d673-130">Backwards compatibility refers to the ability of an existing consumer of an API to run against a new version while behaving in the same way.</span></span> <span data-ttu-id="6d673-131">動作の変更とバイナリの互換性の変更の両方が、下位互換性に影響します。</span><span class="sxs-lookup"><span data-stu-id="6d673-131">Both behavioral changes and changes in binary compatibility affect backwards compatibility.</span></span> <span data-ttu-id="6d673-132">コンシューマーがその API の新しいバージョンで実行されるときに、実行できない、または動作が異なる場合、その API は "*下位非互換*" です。</span><span class="sxs-lookup"><span data-stu-id="6d673-132">If a consumer is not able to run or behaves differently when running against the newer version of the API, the API is *backwards incompatible*.</span></span>

<span data-ttu-id="6d673-133">開発者は新しいバージョンの API が下位互換であることを期待しているので、下位互換性に影響する変更は行わないことを推奨します。</span><span class="sxs-lookup"><span data-stu-id="6d673-133">Changes that affect backwards compatibility are discouraged, since developers expect backwards compatibility in newer versions of an API.</span></span>

## <a name="forward-compatibility"></a><span data-ttu-id="6d673-134">上位互換性</span><span class="sxs-lookup"><span data-stu-id="6d673-134">Forward compatibility</span></span>

<span data-ttu-id="6d673-135">上位互換性とは、API の既存のコンシューマーが、古いバージョンに対して同じ動作を示して実行できることを指します。</span><span class="sxs-lookup"><span data-stu-id="6d673-135">Forward compatibility refers to the ability of an existing consumer of an API to run against an older version while exhibiting the same behavior.</span></span> <span data-ttu-id="6d673-136">コンシューマーがその API の新しいバージョンで実行されるときに、実行できない、または動作が異なる場合、その API は "*上位非互換*" です。</span><span class="sxs-lookup"><span data-stu-id="6d673-136">If a consumer is not able to run or behaves differently when run against an older version of the API, the API is *forward incompatible*.</span></span>

<span data-ttu-id="6d673-137">上位互換を維持するということは、バージョン間でどのような変更や追加も実質的に行わないことを意味します。より新しいバージョンを対象とするコンシューマーが以前のバージョンで実行されるのを、これらの変更が阻止するためです。</span><span class="sxs-lookup"><span data-stu-id="6d673-137">Maintaining forward compatibility virtually precludes any changes or additions from version to version, since those changes prevent a consumer that targets a later version from running under an earlier version.</span></span> <span data-ttu-id="6d673-138">開発者は、より新しい API に依存するコンシューマーが古い API では正しく動作しない場合があると想定しています。</span><span class="sxs-lookup"><span data-stu-id="6d673-138">Developers expect that a consumer that relies on a newer API may not function correctly against the older API.</span></span>

<span data-ttu-id="6d673-139">上位互換性の維持が .NET Core の目標ではないのです。</span><span class="sxs-lookup"><span data-stu-id="6d673-139">Maintaining forward compatibility is not a goal of .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d673-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d673-140">See also</span></span>

- [<span data-ttu-id="6d673-141">.NET Core の破壊的変更を評価する</span><span class="sxs-lookup"><span data-stu-id="6d673-141">Evaluate breaking changes in .NET Core</span></span>](index.md)
