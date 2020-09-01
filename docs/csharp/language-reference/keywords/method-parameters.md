---
description: メソッドのパラメーター - C# リファレンス
title: メソッドのパラメーター - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 7090bf1c3df65cf1e65942404f883b49612e7521
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134407"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="ac2a5-103">メソッドのパラメーター (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ac2a5-103">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="ac2a5-104">[in](./in-parameter-modifier.md)、[ref](./ref.md) または [out](./out-parameter-modifier.md) のないメソッドで宣言されたパラメーターは、呼び出されたメソッドに値で渡されます。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-104">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="ac2a5-105">メソッドでその値を変更できますが、呼び出し元のプロシージャに制御が渡されるときに、変更された値は保持されません。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-105">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="ac2a5-106">メソッド パラメーターのキーワードを使用して、この動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-106">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="ac2a5-107">ここでは、メソッドのパラメーターを宣言するときに使用できるキーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-107">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="ac2a5-108">[params](./params.md) は、このパラメーターが異なる数の引数を取得する可能性があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-108">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="ac2a5-109">[in](./in-parameter-modifier.md) は、このパラメーターが参照によって渡されますが、呼び出されたメソッドでは読み取りのみが行われることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-109">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="ac2a5-110">[ref](./ref.md) は、このパラメーターが参照によって渡され、呼び出されたメソッドでは読み取りまたは書き込みが行われる可能性があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-110">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="ac2a5-111">[out](./out-parameter-modifier.md) は、このパラメーターが参照によって渡され、呼び出されたメソッドでは書き込みが行われることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac2a5-111">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac2a5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac2a5-112">See also</span></span>

- [<span data-ttu-id="ac2a5-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ac2a5-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ac2a5-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ac2a5-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ac2a5-115">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="ac2a5-115">C# Keywords</span></span>](./index.md)
