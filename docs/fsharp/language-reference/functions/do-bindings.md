---
title: do バインド
description: 関数またはF#値を定義せずに ' do ' バインディングを使用してコードを実行する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630530"
---
# <a name="do-bindings"></a><span data-ttu-id="b3684-103">do バインド</span><span class="sxs-lookup"><span data-stu-id="b3684-103">do Bindings</span></span>

<span data-ttu-id="b3684-104">バインディング`do`は、関数または値を定義せずにコードを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3684-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="b3684-105">また、バインディングはクラスで使用できます。「 [ `do`クラスのバインディング](../members/do-bindings-in-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3684-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="b3684-106">構文</span><span class="sxs-lookup"><span data-stu-id="b3684-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="b3684-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3684-107">Remarks</span></span>

<span data-ttu-id="b3684-108">関数また`do`は値の定義とは別にコードを実行する場合は、バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3684-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="b3684-109">`do`バインディング内の式はを返す`unit`必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3684-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="b3684-110">最上位レベル`do`のバインド内のコードは、モジュールが初期化されるときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b3684-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="b3684-111">キーワード`do`は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b3684-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="b3684-112">最上位レベル`do`のバインドに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="b3684-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="b3684-113">たとえば、プログラムが COM 相互運用機能を使用している場合は、 `STAThread`プログラムに属性を適用できます。</span><span class="sxs-lookup"><span data-stu-id="b3684-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="b3684-114">これを行うには、次のコードに`do`示すように、バインディングの属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3684-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="b3684-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3684-115">See also</span></span>

- [<span data-ttu-id="b3684-116">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="b3684-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="b3684-117">関数</span><span class="sxs-lookup"><span data-stu-id="b3684-117">Functions</span></span>](index.md)
