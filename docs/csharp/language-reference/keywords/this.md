---
title: this キーワード - C# リファレンス
description: this キーワード (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715101"
---
# <a name="this-c-reference"></a><span data-ttu-id="b1678-103">this (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b1678-103">this (C# Reference)</span></span>

<span data-ttu-id="b1678-104">`this` キーワードはクラスの現在のインスタンスを参照します。拡張メソッドの最初のパラメーターの修飾子としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1678-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="b1678-105">ここでは、クラス インスタンスでの `this` の使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1678-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="b1678-106">拡張メソッドでの使用の詳細については、「[拡張メソッド](../../programming-guide/classes-and-structs/extension-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1678-106">For more information about its use in extension methods, see [Extension Methods](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="b1678-107">`this` の一般的な使い方を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b1678-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="b1678-108">似た名前によって非表示にされるメンバーを修飾する場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b1678-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="b1678-109">オブジェクトを他のメソッドにパラメーターとして渡す場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b1678-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="b1678-110">インデクサーを宣言する場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b1678-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="b1678-111">静的メンバー関数は、クラス レベルで存在し、オブジェクトの一部ではないため、`this` ポインターがありません。</span><span class="sxs-lookup"><span data-stu-id="b1678-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="b1678-112">静的メソッドで `this` を参照するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="b1678-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="b1678-113">例</span><span class="sxs-lookup"><span data-stu-id="b1678-113">Example</span></span>

<span data-ttu-id="b1678-114">この例では、似た名前によって非表示にされている `Employee` クラスのメンバー `name` と `alias` を修飾するために `this` が使用されています。</span><span class="sxs-lookup"><span data-stu-id="b1678-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="b1678-115">また、別のクラスに属するメソッド `CalcTax` にオブジェクトを渡すためにも使用されています。</span><span class="sxs-lookup"><span data-stu-id="b1678-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="b1678-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b1678-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b1678-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1678-117">See also</span></span>

- [<span data-ttu-id="b1678-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b1678-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b1678-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b1678-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b1678-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b1678-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b1678-121">base</span><span class="sxs-lookup"><span data-stu-id="b1678-121">base</span></span>](base.md)
- [<span data-ttu-id="b1678-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="b1678-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
