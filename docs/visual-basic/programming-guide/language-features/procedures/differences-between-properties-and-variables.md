---
title: プロパティと変数の違い
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: bbed3248840803d36607a67c8373fed15c07445f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341222"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="55c89-102">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="55c89-102">Differences Between Properties and Variables in Visual Basic</span></span>
<span data-ttu-id="55c89-103">変数とプロパティはどちらも、アクセスできる値を表します。</span><span class="sxs-lookup"><span data-stu-id="55c89-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="55c89-104">ただし、ストレージと実装には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="55c89-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="55c89-105">変数:</span><span class="sxs-lookup"><span data-stu-id="55c89-105">Variables</span></span>  
 <span data-ttu-id="55c89-106">*変数*は、メモリ位置に直接対応します。</span><span class="sxs-lookup"><span data-stu-id="55c89-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="55c89-107">1つの宣言ステートメントで変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="55c89-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="55c89-108">変数は、プロシージャ内で定義され、そのプロシージャ内でのみ使用可能な*ローカル変数*にすることができます。また、モジュール、クラス、または構造体で定義されているが、プロシージャ内には定義されていない*メンバー変数*にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="55c89-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="55c89-109">メンバー変数は*フィールド*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="55c89-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="55c89-110">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="55c89-110">Properties</span></span>  
 <span data-ttu-id="55c89-111">*プロパティ*は、モジュール、クラス、または構造体で定義されたデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="55c89-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="55c89-112">`Property` と `End Property` ステートメント間のコードブロックを使用して、プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="55c89-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="55c89-113">コードブロックには、`Get` プロシージャ、`Set` プロシージャ、またはその両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="55c89-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="55c89-114">これらのプロシージャは、*プロパティプロシージャ*または*プロパティアクセサー*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="55c89-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="55c89-115">プロパティの値を取得または格納するだけでなく、アクセスカウンターの更新などのカスタムアクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="55c89-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="55c89-116">[残領域]</span><span class="sxs-lookup"><span data-stu-id="55c89-116">Differences</span></span>  
 <span data-ttu-id="55c89-117">変数とプロパティのいくつかの重要な違いを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="55c89-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="55c89-118">相違点</span><span class="sxs-lookup"><span data-stu-id="55c89-118">Point of difference</span></span>|<span data-ttu-id="55c89-119">変数</span><span class="sxs-lookup"><span data-stu-id="55c89-119">Variable</span></span>|<span data-ttu-id="55c89-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="55c89-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="55c89-121">宣言</span><span class="sxs-lookup"><span data-stu-id="55c89-121">Declaration</span></span>|<span data-ttu-id="55c89-122">単一の宣言ステートメント</span><span class="sxs-lookup"><span data-stu-id="55c89-122">Single declaration statement</span></span>|<span data-ttu-id="55c89-123">コードブロック内の一連のステートメント</span><span class="sxs-lookup"><span data-stu-id="55c89-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="55c89-124">実装</span><span class="sxs-lookup"><span data-stu-id="55c89-124">Implementation</span></span>|<span data-ttu-id="55c89-125">1つのストレージの場所</span><span class="sxs-lookup"><span data-stu-id="55c89-125">Single storage location</span></span>|<span data-ttu-id="55c89-126">実行可能コード (プロパティプロシージャ)</span><span class="sxs-lookup"><span data-stu-id="55c89-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="55c89-127">ストレージ</span><span class="sxs-lookup"><span data-stu-id="55c89-127">Storage</span></span>|<span data-ttu-id="55c89-128">変数の値に直接関連付けられている</span><span class="sxs-lookup"><span data-stu-id="55c89-128">Directly associated with variable's value</span></span>|<span data-ttu-id="55c89-129">通常、内部ストレージは、プロパティの含まれているクラスまたはモジュールの外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="55c89-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="55c89-130">プロパティの値が、格納されている要素として存在しないか、存在しない可能性があります<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55c89-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="55c89-131">実行可能コード</span><span class="sxs-lookup"><span data-stu-id="55c89-131">Executable code</span></span>|<span data-ttu-id="55c89-132">なし</span><span class="sxs-lookup"><span data-stu-id="55c89-132">None</span></span>|<span data-ttu-id="55c89-133">少なくとも1つのプロシージャが必要です</span><span class="sxs-lookup"><span data-stu-id="55c89-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="55c89-134">読み取りと書き込みのアクセス権</span><span class="sxs-lookup"><span data-stu-id="55c89-134">Read and write access</span></span>|<span data-ttu-id="55c89-135">読み取り/書き込みまたは読み取り専用</span><span class="sxs-lookup"><span data-stu-id="55c89-135">Read/write or read-only</span></span>|<span data-ttu-id="55c89-136">読み取り/書き込み、読み取り専用、または書き込み専用</span><span class="sxs-lookup"><span data-stu-id="55c89-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="55c89-137">カスタムアクション (値の受け入れまたは返却に加えて)</span><span class="sxs-lookup"><span data-stu-id="55c89-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="55c89-138">無理です</span><span class="sxs-lookup"><span data-stu-id="55c89-138">Not possible</span></span>|<span data-ttu-id="55c89-139">プロパティ値の設定または取得の一部として実行できます。</span><span class="sxs-lookup"><span data-stu-id="55c89-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="55c89-140"><sup>1</sup>変数とは異なり、プロパティの値がストレージの1つの項目に直接対応していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="55c89-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="55c89-141">利便性やセキュリティを高めるためにストレージが分割されている場合や、値が暗号化された形式で格納されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="55c89-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="55c89-142">このような場合、`Get` プロシージャは、ピースをアセンブルするか、格納されている値の暗号化を解除し、`Set` プロシージャは新しい値を暗号化するか、構成ストレージに分割します。</span><span class="sxs-lookup"><span data-stu-id="55c89-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="55c89-143">プロパティ値は一時的なものである可能性があります。この場合、`Get` プロシージャは、プロパティにアクセスするたびに、その時刻を計算します。</span><span class="sxs-lookup"><span data-stu-id="55c89-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c89-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="55c89-144">See also</span></span>

- [<span data-ttu-id="55c89-145">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="55c89-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="55c89-146">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="55c89-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="55c89-147">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="55c89-147">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="55c89-148">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="55c89-148">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="55c89-149">方法 : プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="55c89-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="55c89-150">方法 : 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="55c89-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="55c89-151">方法 : プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="55c89-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="55c89-152">方法: Visual Basic で既定のプロパティを宣言して呼び出す</span><span class="sxs-lookup"><span data-stu-id="55c89-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="55c89-153">方法 : プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="55c89-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="55c89-154">方法 : プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="55c89-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
