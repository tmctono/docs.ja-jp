---
title: Object データ型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513044"
---
# <a name="object-data-type"></a><span data-ttu-id="36d99-102">Object データ型</span><span class="sxs-lookup"><span data-stu-id="36d99-102">Object Data Type</span></span>

<span data-ttu-id="36d99-103">オブジェクトを参照するアドレスを保持します。</span><span class="sxs-lookup"><span data-stu-id="36d99-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="36d99-104">任意の参照型 (文字列、配列、クラス、またはインターフェイス) を`Object`変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="36d99-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="36d99-105">変数`Object`は、任意の値型 (numeric、 `Boolean`、 `Char` `Date`、、structure、または enumeration) のデータを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="36d99-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="36d99-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="36d99-106">Remarks</span></span>

<span data-ttu-id="36d99-107">データ`Object`型は、アプリケーションで認識される任意のデータ型のデータを指すことができます。</span><span class="sxs-lookup"><span data-stu-id="36d99-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="36d99-108">コンパイル`Object`時に変数が指している可能性のあるデータ型を把握していない場合は、を使用します。</span><span class="sxs-lookup"><span data-stu-id="36d99-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="36d99-109">の`Object`既定値は`Nothing` 、(null 参照) です。</span><span class="sxs-lookup"><span data-stu-id="36d99-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="36d99-110">データの種類</span><span class="sxs-lookup"><span data-stu-id="36d99-110">Data Types</span></span>

<span data-ttu-id="36d99-111">任意のデータ型の変数、定数、または式を`Object`変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="36d99-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="36d99-112">`Object`変数で現在参照されているデータ型を確認するには<xref:System.Type.GetTypeCode%2A> 、 <xref:System.Type?displayProperty=nameWithType>クラスのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="36d99-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="36d99-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36d99-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="36d99-114">`Object`データ型は参照型です。</span><span class="sxs-lookup"><span data-stu-id="36d99-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="36d99-115">ただし、Visual Basic は、 `Object`値型のデータを参照するときに、変数を値型として扱います。</span><span class="sxs-lookup"><span data-stu-id="36d99-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="36d99-116">記憶域</span><span class="sxs-lookup"><span data-stu-id="36d99-116">Storage</span></span>

<span data-ttu-id="36d99-117">参照先のデータ型にかかわらず`Object` 、変数にはデータ値自体は含まれませんが、値へのポインターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="36d99-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="36d99-118">コンピューターのメモリでは常に4バイトを使用しますが、変数の値を表すデータのストレージは含まれません。</span><span class="sxs-lookup"><span data-stu-id="36d99-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="36d99-119">ポインターを使用してデータを検索するコードがあるため`Object` 、値型を保持する変数は、明示的に型指定された変数よりもアクセスが多少遅くなります。</span><span class="sxs-lookup"><span data-stu-id="36d99-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="36d99-120">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="36d99-120">Programming Tips</span></span>

- <span data-ttu-id="36d99-121">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="36d99-121">**Interop Considerations.**</span></span> <span data-ttu-id="36d99-122">.NET Framework 用に作成されていないコンポーネント (オートメーションや COM オブジェクトなど) とやり取りする場合は、他の環境のポインター型が Visual Basic `Object`型と互換性がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="36d99-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="36d99-123">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="36d99-123">**Performance.**</span></span> <span data-ttu-id="36d99-124">`Object`型を使用して宣言する変数は、任意のオブジェクトへの参照を格納するのに十分な柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="36d99-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="36d99-125">ただし、このような変数に対してメソッドまたはプロパティを呼び出すと、常に*遅延バインディング*(実行時) が発生します。</span><span class="sxs-lookup"><span data-stu-id="36d99-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="36d99-126">(コンパイル時に)*事前バインディング*を強制的に実行し、パフォーマンスを向上させるには、特定のクラス名を持つ変数を宣言するか、特定のデータ型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="36d99-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="36d99-127">オブジェクト変数を宣言するときは、汎用<xref:System.OperatingSystem> `Object`化された型ではなく、特定のクラス型を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="36d99-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="36d99-128">また、の<xref:System.Windows.Forms.Control>代わりに、使用可能な最も具体的な<xref:System.Windows.Forms.TextBox>クラスを使用して、そのプロパティとメソッドにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36d99-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="36d99-129">通常は、**オブジェクトブラウザー**の**クラス**の一覧を使用して、使用可能なクラス名を検索できます。</span><span class="sxs-lookup"><span data-stu-id="36d99-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="36d99-130">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="36d99-130">**Widening.**</span></span> <span data-ttu-id="36d99-131">すべてのデータ型とすべての参照型は`Object` 、データ型に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="36d99-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="36d99-132">これは、エラーが`Object` <xref:System.OverflowException?displayProperty=nameWithType>発生することなく、任意の型をに変換できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="36d99-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="36d99-133">ただし、値型と`Object`の間で変換を行う場合、Visual Basic によって、*ボックス*化とボックス化*解除*と呼ばれる操作が実行され、実行速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="36d99-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="36d99-134">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="36d99-134">**Type Characters.**</span></span> <span data-ttu-id="36d99-135">`Object`にリテラルの型文字または識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="36d99-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="36d99-136">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="36d99-136">**Framework Type.**</span></span> <span data-ttu-id="36d99-137">.NET Framework 内の対応する型は<xref:System.Object?displayProperty=nameWithType>クラスです。</span><span class="sxs-lookup"><span data-stu-id="36d99-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="36d99-138">例</span><span class="sxs-lookup"><span data-stu-id="36d99-138">Example</span></span>

<span data-ttu-id="36d99-139">次の例は、 `Object`オブジェクトインスタンスを指す変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="36d99-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="36d99-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="36d99-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="36d99-141">データの種類</span><span class="sxs-lookup"><span data-stu-id="36d99-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="36d99-142">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="36d99-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="36d99-143">変換の概要</span><span class="sxs-lookup"><span data-stu-id="36d99-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="36d99-144">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="36d99-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="36d99-145">方法: 2つのオブジェクトが関係しているかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="36d99-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="36d99-146">方法: 2つのオブジェクトが同一かどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="36d99-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
