---
title: アサーション
description: 内の式のテストのデバッグ機能として 'アサート' 式を使用する方法について説明します、F#プログラミング言語。
ms.date: 05/16/2016
ms.openlocfilehash: c2d97386e87e9b915da490a78fff9aedb9def616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703219"
---
# <a name="assertions"></a><span data-ttu-id="ca65d-103">アサーション</span><span class="sxs-lookup"><span data-stu-id="ca65d-103">Assertions</span></span>

<span data-ttu-id="ca65d-104">`assert`式は、式のテストに使用できるデバッグ機能。</span><span class="sxs-lookup"><span data-stu-id="ca65d-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="ca65d-105">デバッグ モードでエラーが発生すると、アサーションによってシステム エラーのダイアログ ボックスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca65d-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca65d-106">構文</span><span class="sxs-lookup"><span data-stu-id="ca65d-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="ca65d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca65d-107">Remarks</span></span>

<span data-ttu-id="ca65d-108">`assert`式の型`bool -> unit`します。</span><span class="sxs-lookup"><span data-stu-id="ca65d-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="ca65d-109">前の構文で*条件*をテストするブール式を表します。</span><span class="sxs-lookup"><span data-stu-id="ca65d-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="ca65d-110">式が評価された場合`true`実行が影響を受けていないが続行されます。</span><span class="sxs-lookup"><span data-stu-id="ca65d-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="ca65d-111">評価されると、`false`システムのエラー ダイアログ ボックスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca65d-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="ca65d-112">エラー ダイアログ ボックスには、文字列を含むキャプション**アサーションが失敗した**します。</span><span class="sxs-lookup"><span data-stu-id="ca65d-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="ca65d-113">ダイアログ ボックスには、アサーション エラーが発生したかを示すスタック トレースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca65d-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="ca65d-114">デバッグ モードでコンパイルする場合にのみにアサーション チェックが有効にはつまり場合、定数`DEBUG`が定義されています。</span><span class="sxs-lookup"><span data-stu-id="ca65d-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="ca65d-115">既定で、プロジェクト システムで、`DEBUG`リリース構成ではなく、デバッグ構成で定義される定数。</span><span class="sxs-lookup"><span data-stu-id="ca65d-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="ca65d-116">使用してアサーション エラーをキャッチできないF#例外処理します。</span><span class="sxs-lookup"><span data-stu-id="ca65d-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="ca65d-117">`assert`関数に解決<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="ca65d-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="ca65d-118">例</span><span class="sxs-lookup"><span data-stu-id="ca65d-118">Example</span></span>

<span data-ttu-id="ca65d-119">次のコード例の使用を示しています、`assert`式。</span><span class="sxs-lookup"><span data-stu-id="ca65d-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="ca65d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca65d-120">See also</span></span>

- [<span data-ttu-id="ca65d-121">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ca65d-121">F# Language Reference</span></span>](index.md)