---
title: Object データ型
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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343966"
---
# <a name="object-data-type"></a><span data-ttu-id="8b4ca-102">Object データ型</span><span class="sxs-lookup"><span data-stu-id="8b4ca-102">Object Data Type</span></span>

<span data-ttu-id="8b4ca-103">オブジェクトを参照するアドレスを保持します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="8b4ca-104">任意の参照型 (文字列、配列、クラス、またはインターフェイス) を `Object` 変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="8b4ca-105">`Object` 変数は、任意の値型 (数値、`Boolean`、`Char`、`Date`、構造体、または列挙型) のデータを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="8b4ca-106">コメント</span><span class="sxs-lookup"><span data-stu-id="8b4ca-106">Remarks</span></span>

<span data-ttu-id="8b4ca-107">`Object` のデータ型は、アプリケーションで認識される任意のデータ型のデータを指すことができます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="8b4ca-108">コンパイル時に変数が指している可能性のあるデータ型を把握していない場合は、`Object` を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="8b4ca-109">`Object` の既定値は `Nothing` (null 参照) です。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="8b4ca-110">データ型</span><span class="sxs-lookup"><span data-stu-id="8b4ca-110">Data Types</span></span>

<span data-ttu-id="8b4ca-111">任意のデータ型の変数、定数、または式を `Object` 変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="8b4ca-112">`Object` 変数で現在参照されているデータ型を特定するには、<xref:System.Type?displayProperty=nameWithType> クラスの <xref:System.Type.GetTypeCode%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8b4ca-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="8b4ca-114">`Object` データ型は参照型です。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="8b4ca-115">ただし、Visual Basic は、値型のデータを参照するときに、`Object` 変数を値型として扱います。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="8b4ca-116">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8b4ca-116">Storage</span></span>

<span data-ttu-id="8b4ca-117">参照先のデータ型にかかわらず、`Object` 変数にはデータ値自体は含まれませんが、値へのポインターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="8b4ca-118">コンピューターのメモリでは常に4バイトを使用しますが、変数の値を表すデータのストレージは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="8b4ca-119">ポインターを使用してデータを検索するコードのため、`Object` 値型を保持する変数は、明示的に型指定された変数よりもアクセスが多少遅くなります。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="8b4ca-120">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="8b4ca-120">Programming Tips</span></span>

- <span data-ttu-id="8b4ca-121">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-121">**Interop Considerations.**</span></span> <span data-ttu-id="8b4ca-122">.NET Framework 用に作成されていないコンポーネント (オートメーションや COM オブジェクトなど) とやり取りする場合は、他の環境のポインター型が Visual Basic `Object` 型と互換性がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="8b4ca-123">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-123">**Performance.**</span></span> <span data-ttu-id="8b4ca-124">`Object` 型で宣言する変数は、任意のオブジェクトへの参照を格納するのに十分な柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="8b4ca-125">ただし、このような変数に対してメソッドまたはプロパティを呼び出すと、常に*遅延バインディング*(実行時) が発生します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="8b4ca-126">(コンパイル時に)*事前バインディング*を強制的に実行し、パフォーマンスを向上させるには、特定のクラス名を持つ変数を宣言するか、特定のデータ型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="8b4ca-127">オブジェクト変数を宣言するときは、一般化された `Object` 型ではなく、<xref:System.OperatingSystem>などの特定のクラス型を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="8b4ca-128">また、<xref:System.Windows.Forms.Control>ではなく <xref:System.Windows.Forms.TextBox> など、使用可能な最も具体的なクラスを使用して、そのプロパティとメソッドにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="8b4ca-129">通常は、**オブジェクトブラウザー**の**クラス**の一覧を使用して、使用可能なクラス名を検索できます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="8b4ca-130">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-130">**Widening.**</span></span> <span data-ttu-id="8b4ca-131">すべてのデータ型とすべての参照型は、`Object` データ型に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="8b4ca-132">これは、<xref:System.OverflowException?displayProperty=nameWithType> エラーが発生することなく、任意の型を `Object` に変換できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="8b4ca-133">ただし、値型と `Object`の間で変換を行う場合、Visual Basic によって、*ボックス*化と*ボックス化解除*と呼ばれる操作が実行され、実行速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="8b4ca-134">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-134">**Type Characters.**</span></span> <span data-ttu-id="8b4ca-135">`Object` には、リテラルの型文字または識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="8b4ca-136">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-136">**Framework Type.**</span></span> <span data-ttu-id="8b4ca-137">.NET Framework 内の対応する型は、<xref:System.Object?displayProperty=nameWithType> クラスです。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="8b4ca-138">例</span><span class="sxs-lookup"><span data-stu-id="8b4ca-138">Example</span></span>

<span data-ttu-id="8b4ca-139">次の例は、オブジェクトインスタンスを指す `Object` 変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="8b4ca-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b4ca-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="8b4ca-141">データの種類</span><span class="sxs-lookup"><span data-stu-id="8b4ca-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8b4ca-142">CString</span><span class="sxs-lookup"><span data-stu-id="8b4ca-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8b4ca-143">変換の概要</span><span class="sxs-lookup"><span data-stu-id="8b4ca-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8b4ca-144">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="8b4ca-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="8b4ca-145">方法: 2 つのオブジェクトが関連しているかどうかを決める</span><span class="sxs-lookup"><span data-stu-id="8b4ca-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="8b4ca-146">方法: 2 つのオブジェクトが同一であるかどうか判別する</span><span class="sxs-lookup"><span data-stu-id="8b4ca-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
