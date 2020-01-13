---
title: メソッドのパラメーター - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713381"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="7939d-102">メソッドのパラメーター (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7939d-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="7939d-103">[in](./in-parameter-modifier.md)、[ref](./ref.md) または [out](./out-parameter-modifier.md) のないメソッドで宣言されたパラメーターは、呼び出されたメソッドに値で渡されます。</span><span class="sxs-lookup"><span data-stu-id="7939d-103">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="7939d-104">メソッドでその値を変更できますが、呼び出し元のプロシージャに制御が渡されるときに、変更された値は保持されません。</span><span class="sxs-lookup"><span data-stu-id="7939d-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="7939d-105">メソッド パラメーターのキーワードを使用して、この動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7939d-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="7939d-106">ここでは、メソッドのパラメーターを宣言するときに使用できるキーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7939d-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="7939d-107">[params](./params.md) は、このパラメーターが異なる数の引数を取得する可能性があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7939d-107">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="7939d-108">[in](./in-parameter-modifier.md) は、このパラメーターが参照によって渡されますが、呼び出されたメソッドでは読み取りのみが行われることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7939d-108">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="7939d-109">[ref](./ref.md) は、このパラメーターが参照によって渡され、呼び出されたメソッドでは読み取りまたは書き込みが行われる可能性があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7939d-109">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="7939d-110">[out](./out-parameter-modifier.md) は、このパラメーターが参照によって渡され、呼び出されたメソッドでは書き込みが行われることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7939d-110">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7939d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7939d-111">See also</span></span>

- [<span data-ttu-id="7939d-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7939d-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7939d-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7939d-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7939d-114">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="7939d-114">C# Keywords</span></span>](./index.md)
