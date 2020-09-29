---
title: C# で定数を定義する方法
description: C# で定数を定義する方法について説明します。この定数はフィールドであり、コンパイル時にその値が設定されます。 定数を使用して、特殊な値にわかりやすい名前を提供します。
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: dd8c6469c4d72da5588f0dce5314308bcc7e3b95
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91199121"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="94367-104">C\# で定数を定義する方法</span><span class="sxs-lookup"><span data-stu-id="94367-104">How to define constants in C\#</span></span>

<span data-ttu-id="94367-105">定数とは、値がコンパイル時に設定され、変更できないフィールドです。</span><span class="sxs-lookup"><span data-stu-id="94367-105">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="94367-106">定数を使用して、特殊な値の数値リテラル ("マジック ナンバー") の代わりにわかりやすい名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="94367-106">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94367-107">C# では、C と C++ で通常使用される方法で、[#define](../../language-reference/preprocessor-directives/preprocessor-define.md) プリプロセッサ ディレクティブを使用して定数を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="94367-107">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="94367-108">整数型 (`int`、`byte` など) の定数値を定義するには、列挙型を使用します。</span><span class="sxs-lookup"><span data-stu-id="94367-108">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="94367-109">詳細については、「[enum](../../language-reference/builtin-types/enum.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94367-109">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="94367-110">整数型以外の定数を定義する 1 つの方法は、`Constants` という名前の 1 つの静的クラスにそれらをグループ化することです。</span><span class="sxs-lookup"><span data-stu-id="94367-110">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="94367-111">これを行うには、次の例に示すように、クラス名の前に定数へのすべての参照を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="94367-111">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94367-112">例</span><span class="sxs-lookup"><span data-stu-id="94367-112">Example</span></span>  

 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="94367-113">クラス名修飾子を使用すると、定数を使用するユーザーは、それが定数であり、変更できないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="94367-113">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94367-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="94367-114">See also</span></span>

- [<span data-ttu-id="94367-115">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="94367-115">Classes and Structs</span></span>](./index.md)
