---
title: partial 型 - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 551145b9cdf5fa24f3ae365665e8ff06cf5e9307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715205"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="edd4c-102">partial 型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="edd4c-102">partial type (C# Reference)</span></span>

<span data-ttu-id="edd4c-103">部分型定義では、クラス、構造体、またはインターフェイスの定義を複数のファイルに分割することができます。</span><span class="sxs-lookup"><span data-stu-id="edd4c-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="edd4c-104">*File1.cs* 内:</span><span class="sxs-lookup"><span data-stu-id="edd4c-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="edd4c-105">*File2.cs* 宣言内:</span><span class="sxs-lookup"><span data-stu-id="edd4c-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="edd4c-106">解説</span><span class="sxs-lookup"><span data-stu-id="edd4c-106">Remarks</span></span>

<span data-ttu-id="edd4c-107">クラス型、構造体型、またはインターフェイス型を複数のファイルに分割する操作は、大規模なプロジェクトや、[Windows フォーム デザイナー](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)で自動生成されるコードを処理する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="edd4c-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="edd4c-108">部分型には、[部分メソッド](partial-method.md)が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="edd4c-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="edd4c-109">詳細については、「[部分クラスと部分メソッド](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd4c-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="edd4c-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="edd4c-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="edd4c-111">参照</span><span class="sxs-lookup"><span data-stu-id="edd4c-111">See also</span></span>

- [<span data-ttu-id="edd4c-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="edd4c-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="edd4c-113">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="edd4c-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="edd4c-114">修飾子</span><span class="sxs-lookup"><span data-stu-id="edd4c-114">Modifiers</span></span>](index.md)
- [<span data-ttu-id="edd4c-115">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="edd4c-115">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
