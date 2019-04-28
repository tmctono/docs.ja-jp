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
ms.openlocfilehash: 616110145db2796e05509094b1c023daacd68f03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751677"
---
# <a name="object-data-type"></a><span data-ttu-id="67e5a-102">Object データ型</span><span class="sxs-lookup"><span data-stu-id="67e5a-102">Object Data Type</span></span>
<span data-ttu-id="67e5a-103">オブジェクトを参照するアドレスを保持します。</span><span class="sxs-lookup"><span data-stu-id="67e5a-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="67e5a-104">参照型 (文字列、配列、クラス、またはインターフェイス) を割り当てることができます、`Object`変数。</span><span class="sxs-lookup"><span data-stu-id="67e5a-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="67e5a-105">`Object`変数は、任意の値型のデータを指すことも (数値、 `Boolean`、 `Char`、 `Date`、構造体、または列挙型)。</span><span class="sxs-lookup"><span data-stu-id="67e5a-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67e5a-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="67e5a-106">Remarks</span></span>  
 <span data-ttu-id="67e5a-107">`Object`データ型は、アプリケーションが認識済みのオブジェクト インスタンスを含む、任意のデータ型のデータを指すことができます。</span><span class="sxs-lookup"><span data-stu-id="67e5a-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="67e5a-108">使用`Object`コンパイル時にわからない場合をポイントする変数がどのようなデータ型します。</span><span class="sxs-lookup"><span data-stu-id="67e5a-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="67e5a-109">既定値`Object`は`Nothing`(null 参照)。</span><span class="sxs-lookup"><span data-stu-id="67e5a-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="67e5a-110">データの種類</span><span class="sxs-lookup"><span data-stu-id="67e5a-110">Data Types</span></span>  
 <span data-ttu-id="67e5a-111">変数、定数、またはに任意のデータ型の式を割り当てることができます、`Object`変数。</span><span class="sxs-lookup"><span data-stu-id="67e5a-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="67e5a-112">データ型を決定する、`Object`変数を現在参照して、使用することができます、<xref:System.Type.GetTypeCode%2A>のメソッド、<xref:System.Type?displayProperty=nameWithType>クラス。</span><span class="sxs-lookup"><span data-stu-id="67e5a-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="67e5a-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="67e5a-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="67e5a-114">`Object`データ型が参照型。</span><span class="sxs-lookup"><span data-stu-id="67e5a-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="67e5a-115">ただし、Visual Basic の処理、`Object`変数に値型のデータを参照する場合、値型。</span><span class="sxs-lookup"><span data-stu-id="67e5a-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="67e5a-116">記憶域</span><span class="sxs-lookup"><span data-stu-id="67e5a-116">Storage</span></span>  
 <span data-ttu-id="67e5a-117">参照するすべてのデータ型、`Object`自体が、値へのポインターではなく、変数がデータ値を含んでいません。</span><span class="sxs-lookup"><span data-stu-id="67e5a-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="67e5a-118">コンピューターのメモリ内で常に 4 バイトを使用しますが、これは、変数の値を表すデータのストレージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="67e5a-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="67e5a-119">ポインターを使用して、データを検索するコードのため`Object`値の型を保持する変数より明示的に型指定された変数へのアクセスをわずかに遅くなります。</span><span class="sxs-lookup"><span data-stu-id="67e5a-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="67e5a-120">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="67e5a-120">Programming Tips</span></span>  
  
- <span data-ttu-id="67e5a-121">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="67e5a-121">**Interop Considerations.**</span></span> <span data-ttu-id="67e5a-122">オートメーションまたは COM オブジェクトのように、.NET Framework 用に作成されていないコンポーネントとやり取りする場合は、他の環境でのポインター型が、Visual Basic と互換性がないことに留意してください`Object`型。</span><span class="sxs-lookup"><span data-stu-id="67e5a-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
- <span data-ttu-id="67e5a-123">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="67e5a-123">**Performance.**</span></span> <span data-ttu-id="67e5a-124">使用して宣言する変数、`Object`型は柔軟なので、任意のオブジェクトへの参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67e5a-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="67e5a-125">ただし、メソッドまたはプロパティをこのような変数を呼び出すと常に発生*遅延バインディング*(実行時)。</span><span class="sxs-lookup"><span data-stu-id="67e5a-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="67e5a-126">強制的に*事前バインディング*(コンパイル時) より高いパフォーマンスと、特定のクラスの名前を持つ変数を宣言または特定のデータ型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="67e5a-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="67e5a-127">オブジェクト変数を宣言するときに、特定のクラス型を使用して、たとえばしよう<xref:System.OperatingSystem>ではなく、汎用化された`Object`型。</span><span class="sxs-lookup"><span data-stu-id="67e5a-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="67e5a-128">などに使用できる、最も具体的なクラスを使用することも必要があります。<xref:System.Windows.Forms.TextBox>の代わりに<xref:System.Windows.Forms.Control>、そのプロパティとメソッドにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="67e5a-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="67e5a-129">通常使用することができます、**クラス**の一覧で、**オブジェクト ブラウザー**利用可能なクラス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="67e5a-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
- <span data-ttu-id="67e5a-130">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="67e5a-130">**Widening.**</span></span> <span data-ttu-id="67e5a-131">すべてのデータ型とすべての参照型に変換、`Object`データ型。</span><span class="sxs-lookup"><span data-stu-id="67e5a-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="67e5a-132">つまり、任意の種類を変換する`Object`遭遇することがなく、<xref:System.OverflowException?displayProperty=nameWithType>エラー。</span><span class="sxs-lookup"><span data-stu-id="67e5a-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="67e5a-133">ただし、値型の間で変換する場合と`Object`、という操作を実行する Visual Basic*ボックス化*と*ボックス化解除*、実行速度が低下することをします。</span><span class="sxs-lookup"><span data-stu-id="67e5a-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
- <span data-ttu-id="67e5a-134">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="67e5a-134">**Type Characters.**</span></span> <span data-ttu-id="67e5a-135">`Object` リテラルの型文字または識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="67e5a-135">`Object` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="67e5a-136">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="67e5a-136">**Framework Type.**</span></span> <span data-ttu-id="67e5a-137">.NET Framework に対応する型は、<xref:System.Object?displayProperty=nameWithType>クラス。</span><span class="sxs-lookup"><span data-stu-id="67e5a-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67e5a-138">例</span><span class="sxs-lookup"><span data-stu-id="67e5a-138">Example</span></span>  
 <span data-ttu-id="67e5a-139">次の例を示しています、`Object`オブジェクトのインスタンスを指す変数。</span><span class="sxs-lookup"><span data-stu-id="67e5a-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="67e5a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="67e5a-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="67e5a-141">データの種類</span><span class="sxs-lookup"><span data-stu-id="67e5a-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="67e5a-142">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="67e5a-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="67e5a-143">変換の概要</span><span class="sxs-lookup"><span data-stu-id="67e5a-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="67e5a-144">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="67e5a-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="67e5a-145">方法: 2 つのオブジェクトが関連するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="67e5a-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="67e5a-146">方法: 2 つのオブジェクトが同一かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="67e5a-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
