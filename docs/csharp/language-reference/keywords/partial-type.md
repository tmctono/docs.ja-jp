---
title: partial 型 - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 7af43a25f88ff0a53e5fa257b13bb1dc8a6d55eb
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422610"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="28d09-102">partial 型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="28d09-102">partial type (C# Reference)</span></span>

<span data-ttu-id="28d09-103">部分型定義では、クラス、構造体、またはインターフェイスの定義を複数のファイルに分割することができます。</span><span class="sxs-lookup"><span data-stu-id="28d09-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="28d09-104">*File1.cs* 内:</span><span class="sxs-lookup"><span data-stu-id="28d09-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="28d09-105">*File2.cs* 宣言内:</span><span class="sxs-lookup"><span data-stu-id="28d09-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="28d09-106">解説</span><span class="sxs-lookup"><span data-stu-id="28d09-106">Remarks</span></span>

<span data-ttu-id="28d09-107">クラス型、構造体型、またはインターフェイス型を複数のファイルに分割する操作は、大規模なプロジェクトや、[Windows フォーム デザイナー](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)で自動生成されるコードを処理する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28d09-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="28d09-108">部分型には、[部分メソッド](partial-method.md)が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="28d09-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="28d09-109">詳細については、「[部分クラスと部分メソッド](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d09-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="28d09-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="28d09-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="28d09-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="28d09-111">See also</span></span>

- [<span data-ttu-id="28d09-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="28d09-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="28d09-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="28d09-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="28d09-114">修飾子</span><span class="sxs-lookup"><span data-stu-id="28d09-114">Modifiers</span></span>](index.md)
- [<span data-ttu-id="28d09-115">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="28d09-115">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
