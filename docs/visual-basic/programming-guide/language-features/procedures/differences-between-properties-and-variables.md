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
ms.openlocfilehash: 95bafcaca98e1a0fbdd62a550291c8ece932c1ba
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075032"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="c4cab-102">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="c4cab-102">Differences Between Properties and Variables in Visual Basic</span></span>

<span data-ttu-id="c4cab-103">変数とプロパティはどちらも、アクセスできる値を表します。</span><span class="sxs-lookup"><span data-stu-id="c4cab-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="c4cab-104">ただし、ストレージと実装には相違点があります。</span><span class="sxs-lookup"><span data-stu-id="c4cab-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="c4cab-105">変数</span><span class="sxs-lookup"><span data-stu-id="c4cab-105">Variables</span></span>  

 <span data-ttu-id="c4cab-106">"*変数*" は、メモリ位置に直接対応します。</span><span class="sxs-lookup"><span data-stu-id="c4cab-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="c4cab-107">変数は、1 つの宣言ステートメントで定義します。</span><span class="sxs-lookup"><span data-stu-id="c4cab-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="c4cab-108">変数は "*ローカル変数*" (プロシージャ内で定義され、そのプロシージャ内でのみ使用できる) とすることも、"*メンバー変数*" (モジュール、クラス、または構造体内で定義されるが、プロシージャ内では定義されない) とすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="c4cab-109">メンバー変数は "*フィールド*" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c4cab-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c4cab-110">Properties</span></span>  

 <span data-ttu-id="c4cab-111">"*プロパティ*" は、モジュール、クラス、または構造体上で定義されたデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="c4cab-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="c4cab-112">`Property` と `End Property` のステートメント間のコード ブロックを使用してプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c4cab-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="c4cab-113">コード ブロックには、`Get` プロシージャまたは `Set` プロシージャのいずれか、またはその両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="c4cab-114">これらのプロシージャは、"*プロパティ プロシージャ*" または "*プロパティ アクセサー*" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="c4cab-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="c4cab-115">プロパティの値を取得または格納するだけでなく、アクセス カウンターの更新などのカスタム アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="c4cab-116">相違点</span><span class="sxs-lookup"><span data-stu-id="c4cab-116">Differences</span></span>  

 <span data-ttu-id="c4cab-117">次の表に変数とプロパティのいくつかの重要な相違点を示します。</span><span class="sxs-lookup"><span data-stu-id="c4cab-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="c4cab-118">相違点</span><span class="sxs-lookup"><span data-stu-id="c4cab-118">Point of difference</span></span>|<span data-ttu-id="c4cab-119">変数</span><span class="sxs-lookup"><span data-stu-id="c4cab-119">Variable</span></span>|<span data-ttu-id="c4cab-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c4cab-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="c4cab-121">宣言</span><span class="sxs-lookup"><span data-stu-id="c4cab-121">Declaration</span></span>|<span data-ttu-id="c4cab-122">単一の宣言ステートメント</span><span class="sxs-lookup"><span data-stu-id="c4cab-122">Single declaration statement</span></span>|<span data-ttu-id="c4cab-123">コード ブロック内の一連のステートメント</span><span class="sxs-lookup"><span data-stu-id="c4cab-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="c4cab-124">実装</span><span class="sxs-lookup"><span data-stu-id="c4cab-124">Implementation</span></span>|<span data-ttu-id="c4cab-125">単一のストレージ場所</span><span class="sxs-lookup"><span data-stu-id="c4cab-125">Single storage location</span></span>|<span data-ttu-id="c4cab-126">実行可能なコード (プロパティ プロシージャ)</span><span class="sxs-lookup"><span data-stu-id="c4cab-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="c4cab-127">記憶域</span><span class="sxs-lookup"><span data-stu-id="c4cab-127">Storage</span></span>|<span data-ttu-id="c4cab-128">変数の値に直接関連付けられる</span><span class="sxs-lookup"><span data-stu-id="c4cab-128">Directly associated with variable's value</span></span>|<span data-ttu-id="c4cab-129">通常、プロパティの包含クラスまたはモジュールの外部では使用できない内部ストレージがあります。</span><span class="sxs-lookup"><span data-stu-id="c4cab-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="c4cab-130">プロパティの値は格納された要素として存在する場合と存在しない場合があります <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c4cab-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="c4cab-131">実行可能なコード</span><span class="sxs-lookup"><span data-stu-id="c4cab-131">Executable code</span></span>|<span data-ttu-id="c4cab-132">None</span><span class="sxs-lookup"><span data-stu-id="c4cab-132">None</span></span>|<span data-ttu-id="c4cab-133">少なくとも 1 つのプロシージャが必要です。</span><span class="sxs-lookup"><span data-stu-id="c4cab-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="c4cab-134">読み書きアクセス</span><span class="sxs-lookup"><span data-stu-id="c4cab-134">Read and write access</span></span>|<span data-ttu-id="c4cab-135">読み書き、または読み取り専用</span><span class="sxs-lookup"><span data-stu-id="c4cab-135">Read/write or read-only</span></span>|<span data-ttu-id="c4cab-136">読み書き、読み取り専用、または書き込み専用</span><span class="sxs-lookup"><span data-stu-id="c4cab-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="c4cab-137">カスタム アクション (値を受け入れ、または返すことに加えて)</span><span class="sxs-lookup"><span data-stu-id="c4cab-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="c4cab-138">サポートできません</span><span class="sxs-lookup"><span data-stu-id="c4cab-138">Not possible</span></span>|<span data-ttu-id="c4cab-139">プロパティ値の設定または取得の一部として実行できます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="c4cab-140"><sup>1</sup> 変数とは異なり、プロパティの値はストレージの単一の項目に直接対応しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4cab-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="c4cab-141">利便性やセキュリティを高めるためにストレージが各ピースに分割される場合や、値が暗号化された形式で格納される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4cab-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="c4cab-142">このような場合、`Get` プロシージャによって各ピースの組み立てまたは格納されている値の暗号化の解除が行われ、`Set` プロシージャによって新しい値の暗号化または構成ストレージへの分割が行われます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="c4cab-143">プロパティ値は時刻のように一時的なものである可能性があります。その場合は、プロパティにアクセスするたびに `Get` プロシージャによってそれが即座に計算されます。</span><span class="sxs-lookup"><span data-stu-id="c4cab-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4cab-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4cab-144">See also</span></span>

- [<span data-ttu-id="c4cab-145">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c4cab-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="c4cab-146">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="c4cab-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c4cab-147">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="c4cab-147">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="c4cab-148">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="c4cab-148">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="c4cab-149">方法: プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="c4cab-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="c4cab-150">方法: 複数のアクセス レベルを持つプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="c4cab-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="c4cab-151">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c4cab-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="c4cab-152">方法: 既定のプロパティを宣言して呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4cab-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="c4cab-153">方法: プロパティに値を格納する</span><span class="sxs-lookup"><span data-stu-id="c4cab-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="c4cab-154">方法: プロパティから値を取得する</span><span class="sxs-lookup"><span data-stu-id="c4cab-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
