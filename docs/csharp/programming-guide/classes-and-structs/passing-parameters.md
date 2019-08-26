---
title: パラメーターの引き渡し - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 1c42ce7b258ca35d4e91e1ef28c71b60fe1f01de
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596255"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="5d81f-102">パラメーターの引き渡し (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5d81f-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="5d81f-103">C# では、引数を値または参照によってパラメーターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d81f-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="5d81f-104">参照渡しでは、関数メンバー、メソッド、プロパティ、インデクサー、演算子、およびコンストラクターは、パラメーターの値を変更でき、その変更を呼び出し元の環境で永続化できます。</span><span class="sxs-lookup"><span data-stu-id="5d81f-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="5d81f-105">値を変更する目的でパラメーターを参照で渡すには、`ref` または `out` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d81f-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="5d81f-106">値を変更せずにコピーを回避する目的で参照で渡すには、`in` 修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d81f-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="5d81f-107">ここでは、説明を簡単にするために、例に `ref` キーワードだけを使用しています。</span><span class="sxs-lookup"><span data-stu-id="5d81f-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="5d81f-108">`in`、`ref`、`out` の違いの詳細については、[in](../../language-reference/keywords/in-parameter-modifier.md)、[ref](../../language-reference/keywords/ref.md)、[out](../../language-reference/keywords/out-parameter-modifier.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d81f-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="5d81f-109">次の例は、値パラメーターと参照パラメーターの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d81f-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="5d81f-110">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d81f-110">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="5d81f-111">値型パラメーターの引き渡し</span><span class="sxs-lookup"><span data-stu-id="5d81f-111">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="5d81f-112">参照型パラメーターの引き渡し</span><span class="sxs-lookup"><span data-stu-id="5d81f-112">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5d81f-113">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5d81f-113">C# Language Specification</span></span>  

<span data-ttu-id="5d81f-114">詳細については、[C# 言語の仕様](../../language-reference/language-specification/index.md)に関する記事の[引数リスト](~/_csharplang/spec/expressions.md#argument-lists)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d81f-114">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="5d81f-115">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="5d81f-115">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d81f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d81f-116">See also</span></span>

- [<span data-ttu-id="5d81f-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5d81f-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5d81f-118">メソッド</span><span class="sxs-lookup"><span data-stu-id="5d81f-118">Methods</span></span>](./methods.md)
