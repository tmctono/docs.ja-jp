---
title: "'<typename>' はデリゲート型です。"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 45dc0403468fa40888a6c5e6bdfe6ca782e98325
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664196"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="caa85-102">'\<typename>' はデリゲート型です</span><span class="sxs-lookup"><span data-stu-id="caa85-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="caa85-103">'\<typename>' はデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="caa85-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="caa85-104">デリゲート コンストラクションでは、引数リストとして 1 つの AddressOf 式のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="caa85-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="caa85-105">多くの場合、デリゲート コンストラクションの代わりに AddressOf 式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="caa85-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="caa85-106">デリゲート クラスのインスタンスを作成する `New` 句は、デリゲート コンストラクターに無効な引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="caa85-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="caa85-107">新しいデリゲート インスタンスを作成するときは、1 つの `AddressOf` 式のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="caa85-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="caa85-108">このエラーは、デリゲート コンストラクターに引数を渡さない場合、複数の引数を渡した場合、または有効な `AddressOf` 式ではない 1 つの引数を渡した場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="caa85-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="caa85-109">**エラー ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="caa85-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="caa85-110">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="caa85-110">To correct this error</span></span>  
  
- <span data-ttu-id="caa85-111">`New` 句で、デリゲート クラスの引数リストに含まれる 1 つの `AddressOf` 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="caa85-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa85-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="caa85-112">See also</span></span>

- [<span data-ttu-id="caa85-113">New 演算子</span><span class="sxs-lookup"><span data-stu-id="caa85-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="caa85-114">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="caa85-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="caa85-115">デリゲート</span><span class="sxs-lookup"><span data-stu-id="caa85-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="caa85-116">方法: デリゲート メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="caa85-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
