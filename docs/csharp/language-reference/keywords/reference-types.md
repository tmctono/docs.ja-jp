---
description: 参照型 - C# リファレンス
title: 参照型 - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 1a9df3c95d6f5052821be8db5ecf5a8ed99a8ba7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137059"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="27a5c-103">参照型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="27a5c-103">Reference types (C# Reference)</span></span>

<span data-ttu-id="27a5c-104">C# では、参照型と値型という 2 種類の型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="27a5c-104">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="27a5c-105">参照型の変数はデータ (オブジェクト) への参照を格納するのに対して、値型の変数はデータを直接格納します。</span><span class="sxs-lookup"><span data-stu-id="27a5c-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="27a5c-106">参照型の場合、2 つの変数が同じオブジェクトを参照できるため、ある変数に対する演算によって、他の変数が参照しているオブジェクトが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27a5c-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="27a5c-107">値型の場合、各変数が独自のデータ コピーを保持し、ある変数に対する操作が別の変数に影響を与えることはありません (ref および out パラメーター変数の場合を除きます。[in](in-parameter-modifier.md)、[ref](ref.md)、[out](out-parameter-modifier.md) パラメーター修飾子に関するページを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="27a5c-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="27a5c-108">次のキーワードは、参照型を宣言するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="27a5c-108">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="27a5c-109">class</span><span class="sxs-lookup"><span data-stu-id="27a5c-109">class</span></span>](class.md)

- [<span data-ttu-id="27a5c-110">interface</span><span class="sxs-lookup"><span data-stu-id="27a5c-110">interface</span></span>](interface.md)

- [<span data-ttu-id="27a5c-111">delegate</span><span class="sxs-lookup"><span data-stu-id="27a5c-111">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="27a5c-112">C# では次の組み込みの参照型も使用できます。</span><span class="sxs-lookup"><span data-stu-id="27a5c-112">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="27a5c-113">dynamic</span><span class="sxs-lookup"><span data-stu-id="27a5c-113">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="27a5c-114">object</span><span class="sxs-lookup"><span data-stu-id="27a5c-114">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="27a5c-115">string</span><span class="sxs-lookup"><span data-stu-id="27a5c-115">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="27a5c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="27a5c-116">See also</span></span>

- [<span data-ttu-id="27a5c-117">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="27a5c-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="27a5c-118">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="27a5c-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="27a5c-119">ポインター型</span><span class="sxs-lookup"><span data-stu-id="27a5c-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="27a5c-120">値型</span><span class="sxs-lookup"><span data-stu-id="27a5c-120">Value types</span></span>](../builtin-types/value-types.md)
