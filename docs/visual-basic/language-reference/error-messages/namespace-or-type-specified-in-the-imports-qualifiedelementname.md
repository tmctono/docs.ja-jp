---
title: インポート '<qualifiedelementname>' で指定された名前空間または型が、パブリック メンバーを含んでいないか、または見つかりません。
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 1873c0af7a251afd7754557f5dcb6aed13eb9f11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918321"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="cc18a-102">インポートで指定された Namespace または型\<qualifiedelementname >' のパブリック メンバーを含んでいないか、見つかりません</span><span class="sxs-lookup"><span data-stu-id="cc18a-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="cc18a-103">インポートで指定された Namespace または型\<qualifiedelementname >' のパブリック メンバーを含んでいないか、見つかりません。</span><span class="sxs-lookup"><span data-stu-id="cc18a-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="cc18a-104">確認して、名前空間または型が定義されているし、少なくとも 1 つのパブリック メンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc18a-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="cc18a-105">エイリアス名には他のエイリアスが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc18a-105">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="cc18a-106">`Imports`ステートメントがコンテナー要素を検出することはできませんか、いずれかを定義していないいずれかを指定する`Public`メンバー。</span><span class="sxs-lookup"><span data-stu-id="cc18a-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="cc18a-107">A*要素を含む*名前空間、クラス、構造体、モジュール、インターフェイス、または列挙型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc18a-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="cc18a-108">コンテナー要素には、変数、プロシージャ、または他のコンテナー要素などのメンバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc18a-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="cc18a-109">インポートの目的は、それらを修飾することがなくコードの名前空間または型メンバーにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="cc18a-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="cc18a-110">プロジェクトは、名前空間または型への参照を追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="cc18a-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="cc18a-111">詳細については、「を格納している要素のインポート」を参照してください[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc18a-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="cc18a-112">コンパイラに指定されたコンテナー要素が見つからない場合、それを使用して参照を解決できません。</span><span class="sxs-lookup"><span data-stu-id="cc18a-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="cc18a-113">要素を検索しますが、いずれかの要素を公開しません`Public`メンバー、その参照はありませんが成功することができます。</span><span class="sxs-lookup"><span data-stu-id="cc18a-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="cc18a-114">いずれの場合も要素をインポートしても無意味です。</span><span class="sxs-lookup"><span data-stu-id="cc18a-114">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="cc18a-115">コンテナー要素をインポートしてインポート エイリアスを割り当てる場合、使用できないことそのインポート エイリアスを別の要素をインポートすることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="cc18a-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="cc18a-116">次のコードでは、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="cc18a-116">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="cc18a-117">**エラー ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="cc18a-117">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="cc18a-118">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="cc18a-118">To correct this error</span></span>

1. <span data-ttu-id="cc18a-119">コンテナー要素がプロジェクトからアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc18a-119">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="cc18a-120">別のインポートからのインポート エイリアスが含まれている要素の仕様に含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc18a-120">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="cc18a-121">コンテナーの要素が少なくとも 1 つを公開していることを確認します。`Public`メンバー。</span><span class="sxs-lookup"><span data-stu-id="cc18a-121">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc18a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc18a-122">See also</span></span>

- [<span data-ttu-id="cc18a-123">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="cc18a-123">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="cc18a-124">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="cc18a-124">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="cc18a-125">Public</span><span class="sxs-lookup"><span data-stu-id="cc18a-125">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="cc18a-126">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="cc18a-126">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="cc18a-127">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="cc18a-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
