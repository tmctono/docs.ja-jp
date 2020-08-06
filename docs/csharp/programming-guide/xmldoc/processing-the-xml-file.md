---
title: XML ファイルの処理 - C# プログラミング ガイド
description: C# プログラミングにおける XML ファイルの処理方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 6f8a278ed842cd9c4176f3efff423ee048f7e9b9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381542"
---
# <a name="process-the-xml-file-c-programming-guide"></a><span data-ttu-id="bb0b1-104">XML ファイルの処理 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bb0b1-104">Process the XML file (C# programming guide)</span></span>

<span data-ttu-id="bb0b1-105">コンパイラは、ドキュメントを生成するためにタグ付けされたコードのコンストラクトごとに、ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-105">The compiler generates an ID string for each construct in your code that's tagged to generate documentation.</span></span> <span data-ttu-id="bb0b1-106">(コードをタグ付けする方法については、[ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)に関するページを参照してください。)ID 文字列によって、コンストラクトは一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-106">(For information about how to tag your code, see [Recommended Tags for Documentation Comments](./recommended-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="bb0b1-107">XML ファイルを処理するプログラムは、ID 文字列を使用して、対応する .NET のメタデータまたはドキュメントを適用するリフレクション項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-107">Programs that process the XML file can use the ID string to identify the corresponding .NET metadata or reflection item that the documentation applies to.</span></span>

## <a name="id-strings"></a><span data-ttu-id="bb0b1-108">ID 文字列</span><span class="sxs-lookup"><span data-stu-id="bb0b1-108">ID strings</span></span>

<span data-ttu-id="bb0b1-109">.xml ファイルは、コードの階層表現ではなく、</span><span class="sxs-lookup"><span data-stu-id="bb0b1-109">The XML file is not a hierarchical representation of your code.</span></span> <span data-ttu-id="bb0b1-110">要素ごとに生成された ID を持つフラット リストです。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-110">It's a flat list that has a generated ID for each element.</span></span>

<span data-ttu-id="bb0b1-111">コンパイラは、次の規則に基づいて ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-111">The compiler observes the following rules when it generates the ID strings:</span></span>

- <span data-ttu-id="bb0b1-112">文字列に空白文字は含まれません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-112">No white space is in the string.</span></span>

- <span data-ttu-id="bb0b1-113">この文字列の最初の部分は、単一の文字とそれに続くコロンで識別されるメンバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-113">The first part of the string identifies the kind of member using a single character followed by a colon.</span></span> <span data-ttu-id="bb0b1-114">使用されるメンバー型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-114">The following member types are used:</span></span>

    |<span data-ttu-id="bb0b1-115">文字</span><span class="sxs-lookup"><span data-stu-id="bb0b1-115">Character</span></span>|<span data-ttu-id="bb0b1-116">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="bb0b1-116">Member type</span></span>|<span data-ttu-id="bb0b1-117">メモ</span><span class="sxs-lookup"><span data-stu-id="bb0b1-117">Notes</span></span>|
    |---------------|-----------------|-|
    |<span data-ttu-id="bb0b1-118">N</span><span class="sxs-lookup"><span data-stu-id="bb0b1-118">N</span></span>|<span data-ttu-id="bb0b1-119">名前空間</span><span class="sxs-lookup"><span data-stu-id="bb0b1-119">namespace</span></span>|<span data-ttu-id="bb0b1-120">ドキュメント コメントを名前空間に追加することはできませんが、名前空間への cref 参照を行うことはできます (サポートされている場合)。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-120">You cannot add documentation comments to a namespace, but you can make cref references to them, where supported.</span></span>|
    |<span data-ttu-id="bb0b1-121">T</span><span class="sxs-lookup"><span data-stu-id="bb0b1-121">T</span></span>|<span data-ttu-id="bb0b1-122">型</span><span class="sxs-lookup"><span data-stu-id="bb0b1-122">type</span></span>|<span data-ttu-id="bb0b1-123">クラス、インターフェイス、構造体、列挙型、またはデリゲートの型です。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-123">A type can be a class, interface, struct, enum, or delegate.</span></span>|
    |<span data-ttu-id="bb0b1-124">F</span><span class="sxs-lookup"><span data-stu-id="bb0b1-124">F</span></span>|<span data-ttu-id="bb0b1-125">フィールド</span><span class="sxs-lookup"><span data-stu-id="bb0b1-125">field</span></span>|
    |<span data-ttu-id="bb0b1-126">P</span><span class="sxs-lookup"><span data-stu-id="bb0b1-126">P</span></span>|<span data-ttu-id="bb0b1-127">property</span><span class="sxs-lookup"><span data-stu-id="bb0b1-127">property</span></span>|<span data-ttu-id="bb0b1-128">インデクサーまたはその他のインデックス付きプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-128">Includes indexers or other indexed properties.</span></span>|
    |<span data-ttu-id="bb0b1-129">M</span><span class="sxs-lookup"><span data-stu-id="bb0b1-129">M</span></span>|<span data-ttu-id="bb0b1-130">メソッド</span><span class="sxs-lookup"><span data-stu-id="bb0b1-130">method</span></span>|<span data-ttu-id="bb0b1-131">コンストラクターや演算子などの特殊なメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-131">Includes special methods, such as constructors and operators.</span></span>|
    |<span data-ttu-id="bb0b1-132">E</span><span class="sxs-lookup"><span data-stu-id="bb0b1-132">E</span></span>|<span data-ttu-id="bb0b1-133">イベント</span><span class="sxs-lookup"><span data-stu-id="bb0b1-133">event</span></span>|
    |<span data-ttu-id="bb0b1-134">!</span><span class="sxs-lookup"><span data-stu-id="bb0b1-134">!</span></span>|<span data-ttu-id="bb0b1-135">エラー文字列</span><span class="sxs-lookup"><span data-stu-id="bb0b1-135">error string</span></span>|<span data-ttu-id="bb0b1-136">あとに続く文字列で、エラーの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-136">The rest of the string provides information about the error.</span></span> <span data-ttu-id="bb0b1-137">C# コンパイラは、解決できないリンクのエラー情報を生成します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-137">The C# compiler generates error information for links that cannot be resolved.</span></span>|

- <span data-ttu-id="bb0b1-138">文字列の 2 番目の部分は、項目の完全修飾名で、名前空間のルートから始まります。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-138">The second part of the string is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="bb0b1-139">項目の名前、それを囲む型、名前空間は、ピリオドで区切られます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-139">The name of the item, its enclosing type(s), and namespace are separated by periods.</span></span> <span data-ttu-id="bb0b1-140">項目の名前自体にピリオドがある場合、名前のピリオドはハッシュ記号 ('#') に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-140">If the name of the item itself has periods, they are replaced by the hash-sign ('#').</span></span> <span data-ttu-id="bb0b1-141">項目の名前には、ハッシュ記号がないことが前提です。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-141">It's assumed that no item has a hash-sign directly in its name.</span></span> <span data-ttu-id="bb0b1-142">たとえば、String コンストラクターの完全修飾名は "System.String.#ctor" です。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-142">For example, the fully qualified name of the String constructor is "System.String.#ctor".</span></span>

- <span data-ttu-id="bb0b1-143">プロパティおよびメソッドについては、パラメーターのリストをかっこで囲み、プロパティとメソッドに続けて指定します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-143">For properties and methods, the parameter list enclosed in parentheses follows.</span></span> <span data-ttu-id="bb0b1-144">パラメーターがない場合、かっこはありません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-144">If there are no parameters, no parentheses are present.</span></span> <span data-ttu-id="bb0b1-145">パラメーターはコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-145">The parameters are separated by commas.</span></span> <span data-ttu-id="bb0b1-146">各パラメーターのエンコードは、.NET のシグネチャでのエンコード方法にそのまま従います。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-146">The encoding of each parameter follows directly how it's encoded in a .NET signature:</span></span>

  - <span data-ttu-id="bb0b1-147">基本データ型。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-147">Base types.</span></span> <span data-ttu-id="bb0b1-148">通常の型 (ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE) は、型の完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-148">Regular types (ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE) are represented as the fully qualified name of the type.</span></span>

  - <span data-ttu-id="bb0b1-149">(ELEMENT_TYPE_I4、ELEMENT_TYPE_OBJECT、ELEMENT_TYPE_STRING、ELEMENT_TYPE_TYPEDBYREF、および ELEMENT_TYPE_VOID などの) 組み込み型は、対応する完全な型の完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-149">Intrinsic types (for example, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF, and ELEMENT_TYPE_VOID) are represented as the fully qualified name of the corresponding full type.</span></span> <span data-ttu-id="bb0b1-150">たとえば、System.Int32 や System.TypedReference です。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-150">For example, System.Int32 or System.TypedReference.</span></span>

  - <span data-ttu-id="bb0b1-151">ELEMENT_TYPE_PTR は、修飾される型に続けて '\*' と表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-151">ELEMENT_TYPE_PTR is represented as a '\*' following the modified type.</span></span>

  - <span data-ttu-id="bb0b1-152">ELEMENT_TYPE_BYREF は、修飾される型に続けて '\@' と表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-152">ELEMENT_TYPE_BYREF is represented as a '\@' following the modified type.</span></span>

  - <span data-ttu-id="bb0b1-153">ELEMENT_TYPE_PINNED は、修飾される型に続けて '^' と表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-153">ELEMENT_TYPE_PINNED is represented as a '^' following the modified type.</span></span> <span data-ttu-id="bb0b1-154">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-154">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="bb0b1-155">ELEMENT_TYPE_CMOD_REQ は、修飾される型に続けて "&#124;" と修飾子クラスの完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-155">ELEMENT_TYPE_CMOD_REQ is represented as a '&#124;' and the fully qualified name of the modifier class, following the modified type.</span></span> <span data-ttu-id="bb0b1-156">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-156">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="bb0b1-157">ELEMENT_TYPE_CMOD_OPT は、修飾される型に続けて "!" と修飾子クラスの完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-157">ELEMENT_TYPE_CMOD_OPT is represented as a '!' and the fully qualified name of the modifier class, following the modified type.</span></span>

  - <span data-ttu-id="bb0b1-158">ELEMENT_TYPE_SZARRAY は、配列の要素型に続けて "[]" と表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-158">ELEMENT_TYPE_SZARRAY is represented as "[]" following the element type of the array.</span></span>

  - <span data-ttu-id="bb0b1-159">ELEMENT_TYPE_GENERICARRAY は、配列の要素型に続けて "[?]" と表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-159">ELEMENT_TYPE_GENERICARRAY is represented as "[?]" following the element type of the array.</span></span> <span data-ttu-id="bb0b1-160">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-160">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="bb0b1-161">ELEMENT_TYPE_ARRAY は、[*lowerbound*:`size`,*lowerbound*:`size`] の形式で表されます。ここで、コンマの個数はランク -1 個であり、各次元の下限とサイズは明らかな場合は、10 進数で表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-161">ELEMENT_TYPE_ARRAY is represented as [*lowerbound*:`size`,*lowerbound*:`size`] where the number of commas is the rank - 1, and the lower bounds and size of each dimension, if known, are represented in decimal.</span></span> <span data-ttu-id="bb0b1-162">下限またはサイズの指定がない場合は省略されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-162">If a lower bound or size is not specified, it's omitted.</span></span> <span data-ttu-id="bb0b1-163">特定の次元で下限およびサイズが省略されている場合は、':' も省略されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-163">If the lower bound and size for a particular dimension are omitted, the ':' is omitted as well.</span></span> <span data-ttu-id="bb0b1-164">たとえば、ある 2 次元配列の下限が 1 で、サイズの指定がない場合は、[1:,1:] と表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-164">For example, a 2-dimensional array with 1 as the lower bounds and unspecified sizes is [1:,1:].</span></span>

  - <span data-ttu-id="bb0b1-165">ELEMENT_TYPE_FNPTR は、"=FUNC:`type`(*signature*)" と表されます。ここで、`type` は戻り値の型であり、*signature* はメソッドの引数です。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-165">ELEMENT_TYPE_FNPTR is represented as "=FUNC:`type`(*signature*)", where `type` is the return type, and *signature* is the arguments of the method.</span></span> <span data-ttu-id="bb0b1-166">引数がない場合、かっこは省略されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-166">If there are no arguments, the parentheses are omitted.</span></span> <span data-ttu-id="bb0b1-167">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-167">The C# compiler never generates this.</span></span>

  <span data-ttu-id="bb0b1-168">次に示すシグネチャ コンポーネントは、オーバーロードされるメソッドの区別には使用されないため、表されません。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-168">The following signature components aren't represented because they aren't used to differentiate overloaded methods:</span></span>

  - <span data-ttu-id="bb0b1-169">呼び出し規則</span><span class="sxs-lookup"><span data-stu-id="bb0b1-169">calling convention</span></span>

  - <span data-ttu-id="bb0b1-170">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="bb0b1-170">return type</span></span>

  - <span data-ttu-id="bb0b1-171">ELEMENT_TYPE_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="bb0b1-171">ELEMENT_TYPE_SENTINEL</span></span>

- <span data-ttu-id="bb0b1-172">変換演算子 (`op_Implicit` および `op_Explicit`) の場合のみ、メソッドの戻り値が "~" としてエンコードされ、それに続けて戻り値の型が表されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-172">For conversion operators only (`op_Implicit` and `op_Explicit`), the return value of the method is encoded as a '~' followed by the return type.</span></span>

- <span data-ttu-id="bb0b1-173">ジェネリック型では、型の名前の後に、バックチック、ジェネリック型パラメーターの数を示す数値が順に続きます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-173">For generic types, the name of the type is followed by a backtick and then a number that indicates the number of generic type parameters.</span></span> <span data-ttu-id="bb0b1-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-174">For example:</span></span>

     <span data-ttu-id="bb0b1-175">``<member name="T:SampleClass`2">`` は、`public class SampleClass<T, U>` として定義されている型のタグです。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-175">``<member name="T:SampleClass`2">`` is the tag for a type that is defined as `public class SampleClass<T, U>`.</span></span>

     <span data-ttu-id="bb0b1-176">パラメーターとしてジェネリック型を受け取るメソッドでは、ジェネリック型パラメーターは、バックチック付きの数値 (\`0、\`1 など) として指定されます。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-176">For methods that take generic types as parameters, the generic type parameters are specified as numbers prefaced with backticks (for example \`0,\`1).</span></span> <span data-ttu-id="bb0b1-177">各数値は、型のジェネリック パラメーターに対する、0 から始まる配列表記を表しています。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-177">Each number represents a zero-based array notation for the type's generic parameters.</span></span>

## <a name="examples"></a><span data-ttu-id="bb0b1-178">使用例</span><span class="sxs-lookup"><span data-stu-id="bb0b1-178">Examples</span></span>

<span data-ttu-id="bb0b1-179">次の例は、クラスおよびそのメンバーの ID 文字列を生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bb0b1-179">The following examples show how the ID strings for a class and its members are generated:</span></span>

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a><span data-ttu-id="bb0b1-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb0b1-180">See also</span></span>

- [<span data-ttu-id="bb0b1-181">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bb0b1-181">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="bb0b1-182">-doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="bb0b1-182">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="bb0b1-183">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="bb0b1-183">XML documentation comments</span></span>](./index.md)
