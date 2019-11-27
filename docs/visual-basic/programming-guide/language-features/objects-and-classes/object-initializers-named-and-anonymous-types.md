---
title: 'オブジェクト初期化子 : 名前付きの型と匿名型'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 20e46d7ecc206abb28240075d9ec5f764ab78d01
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346131"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="dd676-102">オブジェクト初期化子: 名前付きの型と匿名型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd676-102">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>
<span data-ttu-id="dd676-103">オブジェクト初期化子を使用すると、単一の式を使用して複雑なオブジェクトのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd676-103">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="dd676-104">これらの型を使用して、名前付きの型と匿名型のインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dd676-104">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="dd676-105">宣言</span><span class="sxs-lookup"><span data-stu-id="dd676-105">Declarations</span></span>  
 <span data-ttu-id="dd676-106">名前付きの型と匿名型のインスタンスの宣言はほぼ同じに見えますが、その効果は同じではありません。</span><span class="sxs-lookup"><span data-stu-id="dd676-106">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="dd676-107">各カテゴリには、独自の機能と制限があります。</span><span class="sxs-lookup"><span data-stu-id="dd676-107">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="dd676-108">次の例は、オブジェクト初期化子リストを使用して、`Customer`名前付きクラスのインスタンスを宣言および初期化する便利な方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd676-108">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="dd676-109">キーワード `New`の後に、クラスの名前が指定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd676-109">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 <span data-ttu-id="dd676-110">匿名型には使用可能な名前がありません。</span><span class="sxs-lookup"><span data-stu-id="dd676-110">An anonymous type has no usable name.</span></span> <span data-ttu-id="dd676-111">したがって、匿名型のインスタンス化にクラス名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-111">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 <span data-ttu-id="dd676-112">2つの宣言の要件と結果は同じではありません。</span><span class="sxs-lookup"><span data-stu-id="dd676-112">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="dd676-113">`namedCust`の場合、`Name` プロパティを持つ `Customer` クラスが既に存在している必要があり、宣言によってそのクラスのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-113">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="dd676-114">`anonymousCust`の場合、コンパイラは、1つのプロパティ、`Name`という文字列を持つ新しいクラスを定義し、そのクラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd676-114">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="dd676-115">名前付きの型</span><span class="sxs-lookup"><span data-stu-id="dd676-115">Named Types</span></span>  
 <span data-ttu-id="dd676-116">オブジェクト初期化子は、型のコンストラクターを呼び出す簡単な方法を提供し、1つのステートメントで一部またはすべてのプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd676-116">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="dd676-117">コンパイラは、ステートメントの適切なコンストラクターを呼び出します。引数が指定されていない場合はパラメーターなしのコンストラクター、または1つ以上の引数が送信される場合はパラメーター化されたコンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="dd676-117">The compiler invokes the appropriate constructor for the statement: the parameterless constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="dd676-118">その後、指定されたプロパティは初期化子リストに表示される順序で初期化されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-118">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="dd676-119">初期化子リスト内の各初期化は、クラスのメンバーへの初期値の割り当てで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-119">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="dd676-120">メンバーの名前とデータ型は、クラスが定義されるときに決定されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-120">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="dd676-121">次の例では、`Customer` クラスが存在し、文字列値を受け取ることができる `Name` と `City` という名前のメンバーを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd676-121">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 <span data-ttu-id="dd676-122">または、次のコードを使用して同じ結果を得ることもできます。</span><span class="sxs-lookup"><span data-stu-id="dd676-122">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 <span data-ttu-id="dd676-123">これらの宣言は、次の例と同じです。この例では、パラメーターなしのコンストラクターを使用して `Customer` オブジェクトを作成し、`With` ステートメントを使用して `Name` および `City` プロパティの初期値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="dd676-123">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the parameterless constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 <span data-ttu-id="dd676-124">`Customer` クラスにパラメーター化されたコンストラクターが含まれている場合、たとえば `Name`の値を送信できるようにするには、次の方法で `Customer` オブジェクトを宣言して初期化する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="dd676-124">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 <span data-ttu-id="dd676-125">次のコードに示すように、すべてのプロパティを初期化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dd676-125">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 <span data-ttu-id="dd676-126">ただし、初期化リストを空にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-126">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="dd676-127">初期化されていないプロパティは、既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="dd676-127">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="dd676-128">名前付きの型の推論</span><span class="sxs-lookup"><span data-stu-id="dd676-128">Type Inference with Named Types</span></span>  
 <span data-ttu-id="dd676-129">オブジェクト初期化子とローカル型推論を組み合わせることにより、`cust1` の宣言のコードを短縮できます。</span><span class="sxs-lookup"><span data-stu-id="dd676-129">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="dd676-130">これにより、変数宣言で `As` 句を省略できます。</span><span class="sxs-lookup"><span data-stu-id="dd676-130">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="dd676-131">変数のデータ型は、割り当てによって作成されたオブジェクトの型から推論されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-131">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="dd676-132">次の例では、`cust6` の型が `Customer`です。</span><span class="sxs-lookup"><span data-stu-id="dd676-132">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="dd676-133">名前付きの型に関する解説</span><span class="sxs-lookup"><span data-stu-id="dd676-133">Remarks About Named Types</span></span>  
  
- <span data-ttu-id="dd676-134">オブジェクト初期化子リストでクラスメンバーを複数回初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-134">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="dd676-135">`cust7` の宣言によってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dd676-135">The declaration of `cust7` causes an error.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- <span data-ttu-id="dd676-136">メンバーは、自身または別のフィールドを初期化するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd676-136">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="dd676-137">次の `cust8`の宣言のように、メンバーが初期化される前にアクセスされた場合は、既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-137">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="dd676-138">オブジェクト初期化子を使用する宣言が処理された場合、最初に発生するのは、適切なコンストラクターが呼び出されることです。</span><span class="sxs-lookup"><span data-stu-id="dd676-138">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="dd676-139">その後、初期化子リスト内の個々のフィールドが初期化されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-139">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="dd676-140">次の例では、`Name` の既定値が `cust8`に割り当てられており、初期化された値が `cust9`で割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="dd676-140">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     <span data-ttu-id="dd676-141">次の例では、`cust3` と `cust4` のパラメーター化されたコンストラクターを使用して、`cust10` と `cust11`を宣言および初期化します。</span><span class="sxs-lookup"><span data-stu-id="dd676-141">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- <span data-ttu-id="dd676-142">オブジェクト初期化子は入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd676-142">Object initializers can be nested.</span></span> <span data-ttu-id="dd676-143">次の例では、`AddressClass` は `City` と `State`の2つのプロパティを持つクラスであり、`Customer` クラスには `Address` のインスタンスである `AddressClass`プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="dd676-143">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- <span data-ttu-id="dd676-144">初期化リストを空にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-144">The initialization list cannot be empty.</span></span>  
  
- <span data-ttu-id="dd676-145">初期化するインスタンスを型オブジェクトにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-145">The instance being initialized cannot be of type Object.</span></span>  
  
- <span data-ttu-id="dd676-146">初期化されるクラスメンバーは、共有メンバー、読み取り専用のメンバー、定数、またはメソッドの呼び出しにはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-146">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
- <span data-ttu-id="dd676-147">初期化されるクラスメンバーにインデックスを作成したり、修飾したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-147">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="dd676-148">次の例では、コンパイラエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dd676-148">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="dd676-149">匿名型</span><span class="sxs-lookup"><span data-stu-id="dd676-149">Anonymous Types</span></span>  
 <span data-ttu-id="dd676-150">匿名型では、オブジェクト初期化子を使用して、明示的に定義して名前を指定しない新しい型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd676-150">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="dd676-151">代わりに、コンパイラは、オブジェクト初期化子リストで指定したプロパティに従って型を生成します。</span><span class="sxs-lookup"><span data-stu-id="dd676-151">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="dd676-152">型の名前は指定されていないため、*匿名型*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="dd676-152">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="dd676-153">たとえば、次の宣言を `cust6`の前の宣言と比較します。</span><span class="sxs-lookup"><span data-stu-id="dd676-153">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 <span data-ttu-id="dd676-154">構文が異なるのは、データ型の `New` の後に名前が指定されていないことだけです。</span><span class="sxs-lookup"><span data-stu-id="dd676-154">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="dd676-155">しかし、何が起こるかはかなり異なります。</span><span class="sxs-lookup"><span data-stu-id="dd676-155">However, what happens is quite different.</span></span> <span data-ttu-id="dd676-156">コンパイラは、`Name` と `City`の2つのプロパティを持つ新しい匿名型を定義し、指定された値を使用してそのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd676-156">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="dd676-157">型の推定によって、例の `Name` と `City` の型が文字列になります。</span><span class="sxs-lookup"><span data-stu-id="dd676-157">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="dd676-158">匿名型の名前はコンパイラによって生成され、コンパイルごとに異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd676-158">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="dd676-159">コードでは、匿名型の名前を使用したり、使用したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="dd676-159">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="dd676-160">型の名前は使用できないため、`As` 句を使用して `cust13`を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-160">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="dd676-161">その型を推論する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd676-161">Its type must be inferred.</span></span> <span data-ttu-id="dd676-162">遅延バインディングを使用しない場合、匿名型の使用はローカル変数に限定されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-162">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="dd676-163">匿名型は、[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリに対して重要なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd676-163">Anonymous types provide critical support for [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="dd676-164">クエリでの匿名型の使用の詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」と「 [VISUAL BASIC での LINQ の概要](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd676-164">For more information about the use of anonymous types in queries, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="dd676-165">匿名型の解説</span><span class="sxs-lookup"><span data-stu-id="dd676-165">Remarks About Anonymous Types</span></span>  
  
- <span data-ttu-id="dd676-166">通常、匿名型の宣言に含まれるすべてまたはほとんどのプロパティがキープロパティになります。これは、プロパティ名の前に `Key` キーワードを入力することによって示されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-166">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     <span data-ttu-id="dd676-167">キープロパティの詳細については、「[キー](../../../../visual-basic/language-reference/modifiers/key.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd676-167">For more information about key properties, see [Key](../../../../visual-basic/language-reference/modifiers/key.md).</span></span>  
  
- <span data-ttu-id="dd676-168">名前付きの型の場合と同様に、匿名型の定義の初期化子リストは、少なくとも1つのプロパティを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd676-168">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- <span data-ttu-id="dd676-169">匿名型のインスタンスが宣言されている場合、コンパイラは、一致する匿名型定義を生成します。</span><span class="sxs-lookup"><span data-stu-id="dd676-169">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="dd676-170">プロパティの名前とデータ型は、インスタンス宣言から取得され、コンパイラによって定義に含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd676-170">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="dd676-171">名前付きの型の場合と同じように、プロパティには名前が付けられず、事前に定義されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-171">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="dd676-172">これらの型は推論されます。</span><span class="sxs-lookup"><span data-stu-id="dd676-172">Their types are inferred.</span></span> <span data-ttu-id="dd676-173">`As` 句を使用してプロパティのデータ型を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd676-173">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
- <span data-ttu-id="dd676-174">匿名型では、他のいくつかの方法でプロパティの名前と値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd676-174">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="dd676-175">たとえば、匿名型のプロパティは、変数の名前と値の両方、または別のオブジェクトのプロパティの名前と値の両方を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="dd676-175">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     <span data-ttu-id="dd676-176">匿名型のプロパティを定義するためのオプションの詳細については、「[方法: 匿名型の宣言でプロパティの名前と型を推論](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd676-176">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd676-177">参照</span><span class="sxs-lookup"><span data-stu-id="dd676-177">See also</span></span>

- [<span data-ttu-id="dd676-178">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="dd676-178">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="dd676-179">匿名型</span><span class="sxs-lookup"><span data-stu-id="dd676-179">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="dd676-180">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="dd676-180">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="dd676-181">方法 : 匿名型の宣言におけるプロパティ名と型を推論する</span><span class="sxs-lookup"><span data-stu-id="dd676-181">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="dd676-182">Key</span><span class="sxs-lookup"><span data-stu-id="dd676-182">Key</span></span>](../../../../visual-basic/language-reference/modifiers/key.md)
- [<span data-ttu-id="dd676-183">方法 : オブジェクト初期化子を使用してオブジェクトを宣言する</span><span class="sxs-lookup"><span data-stu-id="dd676-183">How to: Declare an Object by Using an Object Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
