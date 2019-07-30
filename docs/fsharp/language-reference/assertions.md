---
title: アサーション
description: F#プログラミング言語で式をテストするためのデバッグ機能として ' assert ' 式を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630027"
---
# <a name="assertions"></a><span data-ttu-id="54698-103">アサーション</span><span class="sxs-lookup"><span data-stu-id="54698-103">Assertions</span></span>

<span data-ttu-id="54698-104">`assert`式は、式をテストするために使用できるデバッグ機能です。</span><span class="sxs-lookup"><span data-stu-id="54698-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="54698-105">デバッグ モードでエラーが発生すると、アサーションによってシステム エラーのダイアログ ボックスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="54698-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="54698-106">構文</span><span class="sxs-lookup"><span data-stu-id="54698-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="54698-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="54698-107">Remarks</span></span>

<span data-ttu-id="54698-108">式`assert`の型`bool -> unit`がです。</span><span class="sxs-lookup"><span data-stu-id="54698-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="54698-109">前の構文では、 *condition*はテスト対象のブール式を表します。</span><span class="sxs-lookup"><span data-stu-id="54698-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="54698-110">式がに`true`評価された場合、実行は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="54698-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="54698-111">と評価`false`されると、システムエラーダイアログボックスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="54698-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="54698-112">エラーダイアログボックスには、文字列の**アサーションに失敗**したキャプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="54698-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="54698-113">ダイアログボックスには、アサーションエラーが発生した場所を示すスタックトレースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="54698-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="54698-114">アサーションチェックは、デバッグモードでコンパイルした場合にのみ有効になります。つまり、定数`DEBUG`が定義されている場合はです。</span><span class="sxs-lookup"><span data-stu-id="54698-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="54698-115">既定では、プロジェクトシステムでは、 `DEBUG`定数はデバッグ構成で定義されていますが、リリース構成では定義されていません。</span><span class="sxs-lookup"><span data-stu-id="54698-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="54698-116">例外処理を使用しF#てアサーションエラーをキャッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="54698-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="54698-117">関数`assert`は、に<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>解決されます。</span><span class="sxs-lookup"><span data-stu-id="54698-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="54698-118">例</span><span class="sxs-lookup"><span data-stu-id="54698-118">Example</span></span>

<span data-ttu-id="54698-119">次のコード例は、 `assert`式の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54698-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="54698-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="54698-120">See also</span></span>

- [<span data-ttu-id="54698-121">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="54698-121">F# Language Reference</span></span>](index.md)
