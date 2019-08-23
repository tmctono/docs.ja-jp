---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 43507ac8e9b5843e8fa9496737a3d77b3a425a7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963770"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="0e1da-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e1da-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="0e1da-103">プロパティを書き込むことができても読み取ることができないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e1da-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e1da-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e1da-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0e1da-105">ルール</span><span class="sxs-lookup"><span data-stu-id="0e1da-105">Rules</span></span>  
 <span data-ttu-id="0e1da-106">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="0e1da-106">**Declaration Context.**</span></span> <span data-ttu-id="0e1da-107">`WriteOnly` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="0e1da-108">つまり、 `WriteOnly`プロパティの宣言コンテキストはクラス、構造体、またはモジュールである必要があり、ソースファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0e1da-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="0e1da-109">プロパティは、変数では`WriteOnly`なく、として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="0e1da-110">WriteOnly を使用する場合</span><span class="sxs-lookup"><span data-stu-id="0e1da-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="0e1da-111">場合によっては、コンシューマー側のコードで値を設定できても、それが何であるかを検出できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e1da-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="0e1da-112">たとえば、ソーシャル登録番号やパスワードなどの機密データは、設定されていないコンポーネントによるアクセスから保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e1da-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="0e1da-113">このような場合は、 `WriteOnly`プロパティを使用して値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0e1da-114">`WriteOnly`プロパティを定義して使用する場合は、次の追加の保護対策を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0e1da-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="0e1da-115">**オーバーライド.**</span><span class="sxs-lookup"><span data-stu-id="0e1da-115">**Overriding.**</span></span> <span data-ttu-id="0e1da-116">プロパティがクラスのメンバーである場合は、既定の[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)にすることを許可し、 `Overridable`または`MustOverride`を宣言しません。</span><span class="sxs-lookup"><span data-stu-id="0e1da-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="0e1da-117">これにより、派生クラスがオーバーライドを通じて望ましくないアクセスを行うのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="0e1da-118">**アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="0e1da-118">**Access Level.**</span></span> <span data-ttu-id="0e1da-119">プロパティの機微なデータを1つ以上の変数に保持している場合は、他のコードがアクセスできないように[プライベート](../../../visual-basic/language-reference/modifiers/private.md)変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="0e1da-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="0e1da-120">**よる.**</span><span class="sxs-lookup"><span data-stu-id="0e1da-120">**Encryption.**</span></span> <span data-ttu-id="0e1da-121">すべての機密データをプレーンテキストではなく暗号化された形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="0e1da-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="0e1da-122">悪意のあるコードが何らかの方法でメモリ領域にアクセスできた場合は、データを使用するのが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="0e1da-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="0e1da-123">暗号化は、機密データをシリアル化する必要がある場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="0e1da-124">**戻す.**</span><span class="sxs-lookup"><span data-stu-id="0e1da-124">**Resetting.**</span></span> <span data-ttu-id="0e1da-125">プロパティを定義するクラス、構造体、またはモジュールが終了しているときに、機微なデータを既定値またはその他の意味のない値にリセットします。</span><span class="sxs-lookup"><span data-stu-id="0e1da-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="0e1da-126">これにより、メモリの領域が一般アクセス用に解放されるときに、追加の保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="0e1da-127">**永続化.**</span><span class="sxs-lookup"><span data-stu-id="0e1da-127">**Persistence.**</span></span> <span data-ttu-id="0e1da-128">機密データを回避できる場合は、ディスクなどに保存しないでください。</span><span class="sxs-lookup"><span data-stu-id="0e1da-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="0e1da-129">また、機微なデータをクリップボードに書き込まないでください。</span><span class="sxs-lookup"><span data-stu-id="0e1da-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="0e1da-130">修飾子`WriteOnly`は、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e1da-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="0e1da-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="0e1da-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e1da-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e1da-132">See also</span></span>

- [<span data-ttu-id="0e1da-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="0e1da-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="0e1da-134">Private</span><span class="sxs-lookup"><span data-stu-id="0e1da-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="0e1da-135">キーワード</span><span class="sxs-lookup"><span data-stu-id="0e1da-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
