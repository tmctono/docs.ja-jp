---
title: WriteOnly
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
ms.openlocfilehash: 12a1030a423359a3e4122eea98e223a1a02f680c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867623"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="1be07-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1be07-102">WriteOnly (Visual Basic)</span></span>

<span data-ttu-id="1be07-103">プロパティを書き込めるが、読み込みはできないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1be07-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1be07-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="1be07-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1be07-105">ルール</span><span class="sxs-lookup"><span data-stu-id="1be07-105">Rules</span></span>  

 <span data-ttu-id="1be07-106">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="1be07-106">**Declaration Context.**</span></span> <span data-ttu-id="1be07-107">`WriteOnly` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1be07-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="1be07-108">つまり、`WriteOnly` プロパティの宣言コンテキストは、クラス、構造体、またはモジュールにする必要があり、ソース ファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1be07-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="1be07-109">プロパティは、変数ではなく `WriteOnly` として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1be07-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="1be07-110">WriteOnly を使用するタイミング</span><span class="sxs-lookup"><span data-stu-id="1be07-110">When to Use WriteOnly</span></span>  

 <span data-ttu-id="1be07-111">場合によっては、使用しているコードで値を設定できても、それが何であるかを検出できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1be07-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="1be07-112">たとえば、社会登録番号やパスワードなどの機密データは、それが設定されていないコンポーネントからはアクセスできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1be07-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="1be07-113">このような場合は、`WriteOnly` プロパティを使用して値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1be07-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1be07-114">`WriteOnly` プロパティを定義して使用する場合は、次の追加の保護対策を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1be07-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="1be07-115">**オーバーライド。**</span><span class="sxs-lookup"><span data-stu-id="1be07-115">**Overriding.**</span></span> <span data-ttu-id="1be07-116">プロパティがクラスのメンバーである場合は、既定値の [NotOverridable](notoverridable.md) に設定できます。`Overridable` または `MustOverride` としては宣言しないでください。</span><span class="sxs-lookup"><span data-stu-id="1be07-116">If the property is a member of a class, allow it to default to [NotOverridable](notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="1be07-117">これにより、派生クラスがオーバーライドによって不要なアクセスを行うのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="1be07-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="1be07-118">**アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="1be07-118">**Access Level.**</span></span> <span data-ttu-id="1be07-119">プロパティの機密データを 1 つ以上の変数に保持する場合は、他のコードがアクセスできないように、[Private](private.md) として宣言してください。</span><span class="sxs-lookup"><span data-stu-id="1be07-119">If you hold the property's sensitive data in one or more variables, declare them [Private](private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="1be07-120">**暗号化。**</span><span class="sxs-lookup"><span data-stu-id="1be07-120">**Encryption.**</span></span> <span data-ttu-id="1be07-121">すべての機密データを、プレーンテキストではなく暗号化された形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="1be07-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="1be07-122">悪意のあるコードが何らかの方法でメモリ領域にアクセスできた場合は、そのデータを使用するのが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="1be07-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="1be07-123">暗号化は、機密データをシリアル化する必要がある場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1be07-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="1be07-124">**リセット。**</span><span class="sxs-lookup"><span data-stu-id="1be07-124">**Resetting.**</span></span> <span data-ttu-id="1be07-125">プロパティを定義するクラス、構造体、またはモジュールが終了しているときに、機密データを既定値またはその他の意味のない値にリセットします。</span><span class="sxs-lookup"><span data-stu-id="1be07-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="1be07-126">これにより、メモリの領域が一般的なアクセス用に解放されているときに、追加の保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1be07-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="1be07-127">**永続性。**</span><span class="sxs-lookup"><span data-stu-id="1be07-127">**Persistence.**</span></span> <span data-ttu-id="1be07-128">機密データは、ディスクなどにはなるべく保存しないでください。</span><span class="sxs-lookup"><span data-stu-id="1be07-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="1be07-129">また、機密データをクリップボードに書き込まないでください。</span><span class="sxs-lookup"><span data-stu-id="1be07-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="1be07-130">`WriteOnly` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1be07-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="1be07-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="1be07-131">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1be07-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1be07-132">See also</span></span>

- [<span data-ttu-id="1be07-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="1be07-133">ReadOnly</span></span>](readonly.md)
- [<span data-ttu-id="1be07-134">Private</span><span class="sxs-lookup"><span data-stu-id="1be07-134">Private</span></span>](private.md)
- [<span data-ttu-id="1be07-135">キーワード</span><span class="sxs-lookup"><span data-stu-id="1be07-135">Keywords</span></span>](../keywords/index.md)
