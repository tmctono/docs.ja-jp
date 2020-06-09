---
title: XML ファイルの処理 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 1e3d96f9398f2c08ed715111f01987e2d1948439
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287260"
---
# <a name="process-the-xml-file-c-programming-guide"></a><span data-ttu-id="e724f-102">XML ファイルの処理 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e724f-102">Process the XML file (C# programming guide)</span></span>

<span data-ttu-id="e724f-103">コンパイラは、ドキュメントを生成するためにタグ付けされたコードのコンストラクトごとに、ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="e724f-103">The compiler generates an ID string for each construct in your code that's tagged to generate documentation.</span></span> <span data-ttu-id="e724f-104">(コードをタグ付けする方法については、[ドキュメント コメント用の推奨タグ](./recommended-tags-for-documentation-comments.md)に関するページを参照してください。)ID 文字列によって、コンストラクトは一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-104">(For information about how to tag your code, see [Recommended Tags for Documentation Comments](./recommended-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="e724f-105">XML ファイルを処理するプログラムは、ID 文字列を使用して、対応する .NET のメタデータまたはドキュメントを適用するリフレクション項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="e724f-105">Programs that process the XML file can use the ID string to identify the corresponding .NET metadata or reflection item that the documentation applies to.</span></span>

## <a name="id-strings"></a><span data-ttu-id="e724f-106">ID 文字列</span><span class="sxs-lookup"><span data-stu-id="e724f-106">ID strings</span></span>

<span data-ttu-id="e724f-107">.xml ファイルは、コードの階層表現ではなく、</span><span class="sxs-lookup"><span data-stu-id="e724f-107">The XML file is not a hierarchical representation of your code.</span></span> <span data-ttu-id="e724f-108">要素ごとに生成された ID を持つフラット リストです。</span><span class="sxs-lookup"><span data-stu-id="e724f-108">It's a flat list that has a generated ID for each element.</span></span>

<span data-ttu-id="e724f-109">コンパイラは、次の規則に基づいて ID 文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="e724f-109">The compiler observes the following rules when it generates the ID strings:</span></span>

- <span data-ttu-id="e724f-110">文字列に空白文字は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e724f-110">No white space is in the string.</span></span>

- <span data-ttu-id="e724f-111">この文字列の最初の部分は、単一の文字とそれに続くコロンで識別されるメンバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="e724f-111">The first part of the string identifies the kind of member using a single character followed by a colon.</span></span> <span data-ttu-id="e724f-112">使用されるメンバー型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e724f-112">The following member types are used:</span></span>

    |<span data-ttu-id="e724f-113">文字</span><span class="sxs-lookup"><span data-stu-id="e724f-113">Character</span></span>|<span data-ttu-id="e724f-114">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="e724f-114">Member type</span></span>|<span data-ttu-id="e724f-115">メモ</span><span class="sxs-lookup"><span data-stu-id="e724f-115">Notes</span></span>|
    |---------------|-----------------|-|
    |<span data-ttu-id="e724f-116">N</span><span class="sxs-lookup"><span data-stu-id="e724f-116">N</span></span>|<span data-ttu-id="e724f-117">名前空間</span><span class="sxs-lookup"><span data-stu-id="e724f-117">namespace</span></span>|<span data-ttu-id="e724f-118">ドキュメント コメントを名前空間に追加することはできませんが、名前空間への cref 参照を行うことはできます (サポートされている場合)。</span><span class="sxs-lookup"><span data-stu-id="e724f-118">You cannot add documentation comments to a namespace, but you can make cref references to them, where supported.</span></span>|
    |<span data-ttu-id="e724f-119">T</span><span class="sxs-lookup"><span data-stu-id="e724f-119">T</span></span>|<span data-ttu-id="e724f-120">型</span><span class="sxs-lookup"><span data-stu-id="e724f-120">type</span></span>|<span data-ttu-id="e724f-121">クラス、インターフェイス、構造体、列挙型、またはデリゲートの型です。</span><span class="sxs-lookup"><span data-stu-id="e724f-121">A type can be a class, interface, struct, enum, or delegate.</span></span>|
    |<span data-ttu-id="e724f-122">F</span><span class="sxs-lookup"><span data-stu-id="e724f-122">F</span></span>|<span data-ttu-id="e724f-123">フィールド</span><span class="sxs-lookup"><span data-stu-id="e724f-123">field</span></span>|
    |<span data-ttu-id="e724f-124">P</span><span class="sxs-lookup"><span data-stu-id="e724f-124">P</span></span>|<span data-ttu-id="e724f-125">property</span><span class="sxs-lookup"><span data-stu-id="e724f-125">property</span></span>|<span data-ttu-id="e724f-126">インデクサーまたはその他のインデックス付きプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e724f-126">Includes indexers or other indexed properties.</span></span>|
    |<span data-ttu-id="e724f-127">M</span><span class="sxs-lookup"><span data-stu-id="e724f-127">M</span></span>|<span data-ttu-id="e724f-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="e724f-128">method</span></span>|<span data-ttu-id="e724f-129">コンストラクターや演算子などの特殊なメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e724f-129">Includes special methods, such as constructors and operators.</span></span>|
    |<span data-ttu-id="e724f-130">E</span><span class="sxs-lookup"><span data-stu-id="e724f-130">E</span></span>|<span data-ttu-id="e724f-131">イベント</span><span class="sxs-lookup"><span data-stu-id="e724f-131">event</span></span>|
    |<span data-ttu-id="e724f-132">!</span><span class="sxs-lookup"><span data-stu-id="e724f-132">!</span></span>|<span data-ttu-id="e724f-133">エラー文字列</span><span class="sxs-lookup"><span data-stu-id="e724f-133">error string</span></span>|<span data-ttu-id="e724f-134">あとに続く文字列で、エラーの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e724f-134">The rest of the string provides information about the error.</span></span> <span data-ttu-id="e724f-135">C# コンパイラは、解決できないリンクのエラー情報を生成します。</span><span class="sxs-lookup"><span data-stu-id="e724f-135">The C# compiler generates error information for links that cannot be resolved.</span></span>|

- <span data-ttu-id="e724f-136">文字列の 2 番目の部分は、項目の完全修飾名で、名前空間のルートから始まります。</span><span class="sxs-lookup"><span data-stu-id="e724f-136">The second part of the string is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="e724f-137">項目の名前、それを囲む型、名前空間は、ピリオドで区切られます。</span><span class="sxs-lookup"><span data-stu-id="e724f-137">The name of the item, its enclosing type(s), and namespace are separated by periods.</span></span> <span data-ttu-id="e724f-138">項目の名前自体にピリオドがある場合、名前のピリオドはハッシュ記号 ('#') に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e724f-138">If the name of the item itself has periods, they are replaced by the hash-sign ('#').</span></span> <span data-ttu-id="e724f-139">項目の名前には、ハッシュ記号がないことが前提です。</span><span class="sxs-lookup"><span data-stu-id="e724f-139">It's assumed that no item has a hash-sign directly in its name.</span></span> <span data-ttu-id="e724f-140">たとえば、String コンストラクターの完全修飾名は "System.String.#ctor" です。</span><span class="sxs-lookup"><span data-stu-id="e724f-140">For example, the fully qualified name of the String constructor is "System.String.#ctor".</span></span>

- <span data-ttu-id="e724f-141">プロパティおよびメソッドについては、パラメーターのリストをかっこで囲み、プロパティとメソッドに続けて指定します。</span><span class="sxs-lookup"><span data-stu-id="e724f-141">For properties and methods, the parameter list enclosed in parentheses follows.</span></span> <span data-ttu-id="e724f-142">パラメーターがない場合、かっこはありません。</span><span class="sxs-lookup"><span data-stu-id="e724f-142">If there are no parameters, no parentheses are present.</span></span> <span data-ttu-id="e724f-143">パラメーターはコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e724f-143">The parameters are separated by commas.</span></span> <span data-ttu-id="e724f-144">各パラメーターのエンコードは、.NET のシグネチャでのエンコード方法にそのまま従います。</span><span class="sxs-lookup"><span data-stu-id="e724f-144">The encoding of each parameter follows directly how it's encoded in a .NET signature:</span></span>

  - <span data-ttu-id="e724f-145">基本データ型。</span><span class="sxs-lookup"><span data-stu-id="e724f-145">Base types.</span></span> <span data-ttu-id="e724f-146">通常の型 (ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE) は、型の完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-146">Regular types (ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE) are represented as the fully qualified name of the type.</span></span>

  - <span data-ttu-id="e724f-147">(ELEMENT_TYPE_I4、ELEMENT_TYPE_OBJECT、ELEMENT_TYPE_STRING、ELEMENT_TYPE_TYPEDBYREF、および ELEMENT_TYPE_VOID などの) 組み込み型は、対応する完全な型の完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-147">Intrinsic types (for example, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF, and ELEMENT_TYPE_VOID) are represented as the fully qualified name of the corresponding full type.</span></span> <span data-ttu-id="e724f-148">たとえば、System.Int32 や System.TypedReference です。</span><span class="sxs-lookup"><span data-stu-id="e724f-148">For example, System.Int32 or System.TypedReference.</span></span>

  - <span data-ttu-id="e724f-149">ELEMENT_TYPE_PTR は、修飾される型に続けて '\*' と表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-149">ELEMENT_TYPE_PTR is represented as a '\*' following the modified type.</span></span>

  - <span data-ttu-id="e724f-150">ELEMENT_TYPE_BYREF は、修飾される型に続けて '\@' と表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-150">ELEMENT_TYPE_BYREF is represented as a '\@' following the modified type.</span></span>

  - <span data-ttu-id="e724f-151">ELEMENT_TYPE_PINNED は、修飾される型に続けて '^' と表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-151">ELEMENT_TYPE_PINNED is represented as a '^' following the modified type.</span></span> <span data-ttu-id="e724f-152">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="e724f-152">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="e724f-153">ELEMENT_TYPE_CMOD_REQ は、修飾される型に続けて "&#124;" と修飾子クラスの完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-153">ELEMENT_TYPE_CMOD_REQ is represented as a '&#124;' and the fully qualified name of the modifier class, following the modified type.</span></span> <span data-ttu-id="e724f-154">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="e724f-154">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="e724f-155">ELEMENT_TYPE_CMOD_OPT は、修飾される型に続けて "!" と修飾子クラスの完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-155">ELEMENT_TYPE_CMOD_OPT is represented as a '!' and the fully qualified name of the modifier class, following the modified type.</span></span>

  - <span data-ttu-id="e724f-156">ELEMENT_TYPE_SZARRAY は、配列の要素型に続けて "[]" と表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-156">ELEMENT_TYPE_SZARRAY is represented as "[]" following the element type of the array.</span></span>

  - <span data-ttu-id="e724f-157">ELEMENT_TYPE_GENERICARRAY は、配列の要素型に続けて "[?]" と表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-157">ELEMENT_TYPE_GENERICARRAY is represented as "[?]" following the element type of the array.</span></span> <span data-ttu-id="e724f-158">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="e724f-158">The C# compiler never generates this.</span></span>

  - <span data-ttu-id="e724f-159">ELEMENT_TYPE_ARRAY は、[*lowerbound*:`size`,*lowerbound*:`size`] の形式で表されます。ここで、コンマの個数はランク -1 個であり、各次元の下限とサイズは明らかな場合は、10 進数で表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-159">ELEMENT_TYPE_ARRAY is represented as [*lowerbound*:`size`,*lowerbound*:`size`] where the number of commas is the rank - 1, and the lower bounds and size of each dimension, if known, are represented in decimal.</span></span> <span data-ttu-id="e724f-160">下限またはサイズの指定がない場合は省略されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-160">If a lower bound or size is not specified, it's omitted.</span></span> <span data-ttu-id="e724f-161">特定の次元で下限およびサイズが省略されている場合は、':' も省略されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-161">If the lower bound and size for a particular dimension are omitted, the ':' is omitted as well.</span></span> <span data-ttu-id="e724f-162">たとえば、ある 2 次元配列の下限が 1 で、サイズの指定がない場合は、[1:,1:] と表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-162">For example, a 2-dimensional array with 1 as the lower bounds and unspecified sizes is [1:,1:].</span></span>

  - <span data-ttu-id="e724f-163">ELEMENT_TYPE_FNPTR は、"=FUNC:`type`(*signature*)" と表されます。ここで、`type` は戻り値の型であり、*signature* はメソッドの引数です。</span><span class="sxs-lookup"><span data-stu-id="e724f-163">ELEMENT_TYPE_FNPTR is represented as "=FUNC:`type`(*signature*)", where `type` is the return type, and *signature* is the arguments of the method.</span></span> <span data-ttu-id="e724f-164">引数がない場合、かっこは省略されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-164">If there are no arguments, the parentheses are omitted.</span></span> <span data-ttu-id="e724f-165">これは C# コンパイラでは生成されません。</span><span class="sxs-lookup"><span data-stu-id="e724f-165">The C# compiler never generates this.</span></span>

  <span data-ttu-id="e724f-166">次に示すシグネチャ コンポーネントは、オーバーロードされるメソッドの区別には使用されないため、表されません。</span><span class="sxs-lookup"><span data-stu-id="e724f-166">The following signature components aren't represented because they aren't used to differentiate overloaded methods:</span></span>

  - <span data-ttu-id="e724f-167">呼び出し規則</span><span class="sxs-lookup"><span data-stu-id="e724f-167">calling convention</span></span>

  - <span data-ttu-id="e724f-168">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="e724f-168">return type</span></span>

  - <span data-ttu-id="e724f-169">ELEMENT_TYPE_SENTINEL</span><span class="sxs-lookup"><span data-stu-id="e724f-169">ELEMENT_TYPE_SENTINEL</span></span>

- <span data-ttu-id="e724f-170">変換演算子 (`op_Implicit` および `op_Explicit`) の場合のみ、メソッドの戻り値が "~" としてエンコードされ、それに続けて戻り値の型が表されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-170">For conversion operators only (`op_Implicit` and `op_Explicit`), the return value of the method is encoded as a '~' followed by the return type.</span></span>

- <span data-ttu-id="e724f-171">ジェネリック型では、型の名前の後に、バックチック、ジェネリック型パラメーターの数を示す数値が順に続きます。</span><span class="sxs-lookup"><span data-stu-id="e724f-171">For generic types, the name of the type is followed by a backtick and then a number that indicates the number of generic type parameters.</span></span> <span data-ttu-id="e724f-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e724f-172">For example:</span></span>

     <span data-ttu-id="e724f-173">``<member name="T:SampleClass`2">`` は、`public class SampleClass<T, U>` として定義されている型のタグです。</span><span class="sxs-lookup"><span data-stu-id="e724f-173">``<member name="T:SampleClass`2">`` is the tag for a type that is defined as `public class SampleClass<T, U>`.</span></span>

     <span data-ttu-id="e724f-174">パラメーターとしてジェネリック型を受け取るメソッドでは、ジェネリック型パラメーターは、バックチック付きの数値 (\`0、\`1 など) として指定されます。</span><span class="sxs-lookup"><span data-stu-id="e724f-174">For methods that take generic types as parameters, the generic type parameters are specified as numbers prefaced with backticks (for example \`0,\`1).</span></span> <span data-ttu-id="e724f-175">各数値は、型のジェネリック パラメーターに対する、0 から始まる配列表記を表しています。</span><span class="sxs-lookup"><span data-stu-id="e724f-175">Each number represents a zero-based array notation for the type's generic parameters.</span></span>

## <a name="examples"></a><span data-ttu-id="e724f-176">使用例</span><span class="sxs-lookup"><span data-stu-id="e724f-176">Examples</span></span>

<span data-ttu-id="e724f-177">次の例は、クラスおよびそのメンバーの ID 文字列を生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e724f-177">The following examples show how the ID strings for a class and its members are generated:</span></span>

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a><span data-ttu-id="e724f-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="e724f-178">See also</span></span>

- [<span data-ttu-id="e724f-179">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e724f-179">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e724f-180">-doc (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="e724f-180">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="e724f-181">XML ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="e724f-181">XML documentation comments</span></span>](./index.md)
