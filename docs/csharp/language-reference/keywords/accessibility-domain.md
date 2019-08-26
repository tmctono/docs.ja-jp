---
title: アクセシビリティ ドメイン - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 814aa8d3965674abe8bdb60b738cbeff93701ceb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606132"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="d1e74-102">アクセシビリティ ドメイン (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d1e74-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="d1e74-103">メンバーのアクセシビリティ ドメインとは、どのプログラム セクションをメンバーから参照できるかを規定するものです。</span><span class="sxs-lookup"><span data-stu-id="d1e74-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="d1e74-104">そのメンバーが他の型の入れ子になっている場合、そのアクセシビリティ ドメインは、そのメンバーの[アクセシビリティ レベル](./accessibility-levels.md)と、その直接のコンテナーである型のアクセシビリティ ドメインとの両方によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="d1e74-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](./accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="d1e74-105">トップレベルの型のアクセシビリティ ドメインは、それが宣言されているプロジェクトのプログラム テキストと同じかそれ以上になります。</span><span class="sxs-lookup"><span data-stu-id="d1e74-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="d1e74-106">つまり、そのプロジェクトのすべてのソース ファイルがアクセシビリティ ドメインに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1e74-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="d1e74-107">入れ子にされた型のアクセシビリティ ドメインは、それが宣言されている型のプログラム テキストと同じかそれ以上になります。</span><span class="sxs-lookup"><span data-stu-id="d1e74-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="d1e74-108">つまり、アクセシビリティ ドメインは型の本体 (入れ子にされたすべての型のコンテナー) です。</span><span class="sxs-lookup"><span data-stu-id="d1e74-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="d1e74-109">入れ子にされた型のアクセシビリティ ドメインが、その型を含んでいる型のアクセシビリティ ドメインを超えることはありません。</span><span class="sxs-lookup"><span data-stu-id="d1e74-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="d1e74-110">次の例では、以上の概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="d1e74-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1e74-111">例</span><span class="sxs-lookup"><span data-stu-id="d1e74-111">Example</span></span>  
 <span data-ttu-id="d1e74-112">この例には、トップレベルの型 `T1` があり、そこに `M1` と `M2` の 2 つのクラスが入れ子にされています。</span><span class="sxs-lookup"><span data-stu-id="d1e74-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="d1e74-113">これらのクラスには、それぞれ異なるアクセシビリティが宣言されたいくつかのフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="d1e74-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="d1e74-114">`Main` メソッドの各ステートメントには、それぞれのメンバーのアクセシビリティ ドメインを示したコメントが記述されています。</span><span class="sxs-lookup"><span data-stu-id="d1e74-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="d1e74-115">アクセスできないメンバーを参照するステートメントがコメント アウトされていることに注目してください。アクセスできないメンバーを参照したことが原因で発生するコンパイラ エラーを確認したい場合は、1 つずつコメントを解除してください。</span><span class="sxs-lookup"><span data-stu-id="d1e74-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="d1e74-116">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d1e74-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1e74-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1e74-117">See also</span></span>

- [<span data-ttu-id="d1e74-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d1e74-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d1e74-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d1e74-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d1e74-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="d1e74-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d1e74-121">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="d1e74-121">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d1e74-122">アクセシビリティ レベル</span><span class="sxs-lookup"><span data-stu-id="d1e74-122">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="d1e74-123">アクセシビリティ レベルの使用に関する制限事項</span><span class="sxs-lookup"><span data-stu-id="d1e74-123">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="d1e74-124">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="d1e74-124">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="d1e74-125">public</span><span class="sxs-lookup"><span data-stu-id="d1e74-125">public</span></span>](./public.md)
- [<span data-ttu-id="d1e74-126">private</span><span class="sxs-lookup"><span data-stu-id="d1e74-126">private</span></span>](./private.md)
- [<span data-ttu-id="d1e74-127">protected</span><span class="sxs-lookup"><span data-stu-id="d1e74-127">protected</span></span>](./protected.md)
- [<span data-ttu-id="d1e74-128">internal</span><span class="sxs-lookup"><span data-stu-id="d1e74-128">internal</span></span>](./internal.md)
