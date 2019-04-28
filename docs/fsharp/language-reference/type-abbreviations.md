---
title: 型略称
description: コードを読みやすくためにわかりやすい名前の型を提供する F# 型略称について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 0deaef789367aad413e5a537bf7164034e1275c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683341"
---
# <a name="type-abbreviations"></a><span data-ttu-id="868d1-103">型略称</span><span class="sxs-lookup"><span data-stu-id="868d1-103">Type Abbreviations</span></span>

<span data-ttu-id="868d1-104">A*型略称*エイリアスまたは代替名の種類。</span><span class="sxs-lookup"><span data-stu-id="868d1-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="868d1-105">構文</span><span class="sxs-lookup"><span data-stu-id="868d1-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="868d1-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="868d1-106">Remarks</span></span>

<span data-ttu-id="868d1-107">型の省略形を使用すると、コードを読みやすくために、型、わかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="868d1-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="868d1-108">書き込みに面倒なタイプの使いやすい名を作成するのにことも使用できます。さらに、型の省略形を使用すると、型を使用するすべてのコードを変更することがなく、基になる型を変更しやすきます。</span><span class="sxs-lookup"><span data-stu-id="868d1-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="868d1-109">単純な型の省略形を次に示します。</span><span class="sxs-lookup"><span data-stu-id="868d1-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="868d1-110">既定値の型の省略形のアクセシビリティ`public`します。</span><span class="sxs-lookup"><span data-stu-id="868d1-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="868d1-111">型の省略形は、次のコードのように、ジェネリック パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="868d1-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="868d1-112">上記のコードで`Transform`を任意の型の 1 つの引数を受け取る関数を表す型の省略形は、同じ型の 1 つの値を返します。</span><span class="sxs-lookup"><span data-stu-id="868d1-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="868d1-113">型の省略形は、.NET Framework の MSIL コードでは保持されません。</span><span class="sxs-lookup"><span data-stu-id="868d1-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="868d1-114">したがって、F# アセンブリ .NET Framework の別の言語からを使用する場合は、型の省略形の基になる種類の名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="868d1-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="868d1-115">型の省略形は、測定単位にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="868d1-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="868d1-116">詳細については、次を参照してください。[単位](units-of-measure.md)します。</span><span class="sxs-lookup"><span data-stu-id="868d1-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="868d1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="868d1-117">See also</span></span>

- [<span data-ttu-id="868d1-118">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="868d1-118">F# Language Reference</span></span>](index.md)