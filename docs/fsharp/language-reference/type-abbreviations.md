---
title: 型略称
description: コードを読みやすくためにわかりやすい名前の型を提供する F# 型略称について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630217"
---
# <a name="type-abbreviations"></a><span data-ttu-id="e1afe-103">型略称</span><span class="sxs-lookup"><span data-stu-id="e1afe-103">Type Abbreviations</span></span>

<span data-ttu-id="e1afe-104">*型略称*は、型の別名または代替名です。</span><span class="sxs-lookup"><span data-stu-id="e1afe-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="e1afe-105">構文</span><span class="sxs-lookup"><span data-stu-id="e1afe-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="e1afe-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1afe-106">Remarks</span></span>

<span data-ttu-id="e1afe-107">型の省略形を使用すると、コードを読みやすくするために、型にわかりやすい名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e1afe-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="e1afe-108">また、これを使用して、書き込みが煩雑な型の使いやすい名前を作成することもできます。また、型の省略形を使用すると、型を使用するすべてのコードを変更することなく、基になる型を簡単に変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1afe-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="e1afe-109">単純型の省略形を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e1afe-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="e1afe-110">型の省略形のアクセシビリティ`public`は、既定でに設定されています。</span><span class="sxs-lookup"><span data-stu-id="e1afe-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="e1afe-111">次のコードのように、型の省略形にジェネリックパラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e1afe-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="e1afe-112">前のコードでは`Transform` 、は、任意の型の単一の引数を受け取り、同じ型の単一の値を返す関数を表す型略称です。</span><span class="sxs-lookup"><span data-stu-id="e1afe-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="e1afe-113">型の省略形は .NET Framework MSIL コードに保持されません。</span><span class="sxs-lookup"><span data-stu-id="e1afe-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="e1afe-114">したがって、F# アセンブリ .NET Framework の別の言語からを使用する場合は、型の省略形の基になる種類の名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1afe-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="e1afe-115">型略称は、測定単位でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1afe-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="e1afe-116">詳細については、「[測定単位](units-of-measure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1afe-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1afe-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1afe-117">See also</span></span>

- [<span data-ttu-id="e1afe-118">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e1afe-118">F# Language Reference</span></span>](index.md)
