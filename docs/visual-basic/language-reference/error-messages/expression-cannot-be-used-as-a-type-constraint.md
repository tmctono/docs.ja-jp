---
title: "'<expression>' を型制約として使用することはできません。"
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 4f1db6bdbe6f25d0362b55acd95e716fbc2417ed
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874277"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="f68b8-102">'\<expression>' を型制約として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f68b8-102">'\<expression>' cannot be used as a type constraint</span></span>

<span data-ttu-id="f68b8-103">制約リストに、型パラメーターについて有効な制約を表していない式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f68b8-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="f68b8-104">制約リストでは、型パラメーターに渡される型引数の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f68b8-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="f68b8-105">次の要件を任意の組み合わせで指定できます。</span><span class="sxs-lookup"><span data-stu-id="f68b8-105">You can specify the following requirements in any combination:</span></span>  
  
- <span data-ttu-id="f68b8-106">型引数が 1 つまたは複数のインターフェイスを実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="f68b8-106">The type argument must implement one or more interfaces</span></span>  
  
- <span data-ttu-id="f68b8-107">型引数は、最大で 1 つのクラスから継承する必要があります</span><span class="sxs-lookup"><span data-stu-id="f68b8-107">The type argument must inherit from at most one class</span></span>  
  
- <span data-ttu-id="f68b8-108">型引数は、作成元のコードがアクセスできるパラメーターなしのコンストラクターを公開する必要があります ( `New` 制約を含む)</span><span class="sxs-lookup"><span data-stu-id="f68b8-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="f68b8-109">制約リストに特定のクラスまたはインターフェイスを何も含めない場合は、次のいずれかを指定することによって一般的な要件を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f68b8-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
- <span data-ttu-id="f68b8-110">型引数は値型である必要があります ( `Structure` 制約を含む)</span><span class="sxs-lookup"><span data-stu-id="f68b8-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
- <span data-ttu-id="f68b8-111">型引数は参照型である必要があります ( `Class` 制約を含む)</span><span class="sxs-lookup"><span data-stu-id="f68b8-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="f68b8-112">同じ型パラメーターに `Structure` と `Class` の両方を指定することはできません。また、どちらも複数回指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f68b8-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="f68b8-113">**エラー ID:** BC32061</span><span class="sxs-lookup"><span data-stu-id="f68b8-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f68b8-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f68b8-114">To correct this error</span></span>  
  
- <span data-ttu-id="f68b8-115">式とその要素のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f68b8-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
- <span data-ttu-id="f68b8-116">式が上記の要件リストを満たしていない場合は、制約リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="f68b8-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
- <span data-ttu-id="f68b8-117">式でインターフェイスまたはクラスを参照する場合、コンパイラにそのインターフェイスまたはクラスへのアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f68b8-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="f68b8-118">その名前を修飾し、プロジェクトに参照を追加することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f68b8-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="f68b8-119">詳細については、「[宣言された要素の参照](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)」の「プロジェクトへの参照」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f68b8-119">For more information, see "References to Projects" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68b8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f68b8-120">See also</span></span>

- [<span data-ttu-id="f68b8-121">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f68b8-121">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="f68b8-122">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="f68b8-122">Value Types and Reference Types</span></span>](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="f68b8-123">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="f68b8-123">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
