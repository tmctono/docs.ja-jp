---
title: 属性
description: 属性がF#プログラミングコンストラクトにメタデータを適用できるようにする方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 1e42dc61d44f31930a7b34799f28a68a2db69c8c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504119"
---
# <a name="attributes"></a><span data-ttu-id="50a94-103">属性</span><span class="sxs-lookup"><span data-stu-id="50a94-103">Attributes</span></span>

<span data-ttu-id="50a94-104">属性を使用すると、プログラミング構成要素にメタデータを適用できます。</span><span class="sxs-lookup"><span data-stu-id="50a94-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="50a94-105">構文</span><span class="sxs-lookup"><span data-stu-id="50a94-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="50a94-106">コメント</span><span class="sxs-lookup"><span data-stu-id="50a94-106">Remarks</span></span>

<span data-ttu-id="50a94-107">前の構文では、*ターゲット*は省略可能であり、存在する場合は、属性が適用されるプログラムエンティティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="50a94-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="50a94-108">*Target*の有効な値は、このドキュメントの後半で示す表に示されています。</span><span class="sxs-lookup"><span data-stu-id="50a94-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="50a94-109">*属性名*は、有効な属性型の名前 (名前空間で修飾されている可能性があります) を参照します。この名前は、通常、属性の型名で使用される `Attribute` サフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="50a94-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="50a94-110">たとえば、`ObsoleteAttribute` 型を短縮して、このコンテキストで `Obsolete` だけにすることができます。</span><span class="sxs-lookup"><span data-stu-id="50a94-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="50a94-111">*引数*は、属性の型のコンストラクターへの引数です。</span><span class="sxs-lookup"><span data-stu-id="50a94-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="50a94-112">属性にパラメーターなしのコンストラクターがある場合は、引数リストとかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="50a94-112">If an attribute has a parameterless constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="50a94-113">属性は、位置指定引数と名前付き引数の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="50a94-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="50a94-114">*位置指定引数*は、出現する順序で使用される引数です。</span><span class="sxs-lookup"><span data-stu-id="50a94-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="50a94-115">名前付き引数は、属性にパブリックプロパティがある場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="50a94-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="50a94-116">これらを設定するには、引数リストで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="50a94-116">You can set these by using the following syntax in the argument list.</span></span>

```fsharp
property-name = property-value
```

<span data-ttu-id="50a94-117">このようなプロパティの初期化は任意の順序で行うことができますが、任意の位置指定引数に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="50a94-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="50a94-118">位置指定引数とプロパティの初期化を使用する属性の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="50a94-118">The following is an example of an attribute that uses positional arguments and property initializations:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="50a94-119">この例では、属性は `DllImportAttribute`であり、短縮形で使用されています。</span><span class="sxs-lookup"><span data-stu-id="50a94-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="50a94-120">最初の引数は位置指定パラメーターで、2番目の引数はプロパティです。</span><span class="sxs-lookup"><span data-stu-id="50a94-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="50a94-121">属性は、*属性*と呼ばれるオブジェクトが型または他のプログラム要素に関連付けられるようにする .net プログラミングコンストラクトです。</span><span class="sxs-lookup"><span data-stu-id="50a94-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="50a94-122">属性が適用されるプログラム要素は、*属性ターゲット*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="50a94-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="50a94-123">属性には、通常、ターゲットに関するメタデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="50a94-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="50a94-124">このコンテキストでは、メタデータは、フィールドやメンバー以外の型に関する任意のデータにすることができます。</span><span class="sxs-lookup"><span data-stu-id="50a94-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="50a94-125">のF#属性は、関数、メソッド、アセンブリ、モジュール、型 (クラス、レコード、構造体、インターフェイス、デリゲート、列挙体、共用体など)、コンストラクター、プロパティ、フィールド、パラメーター、型パラメーター、および戻り値に適用できます。</span><span class="sxs-lookup"><span data-stu-id="50a94-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="50a94-126">属性は、クラス、式、またはワークフロー式内の `let` バインドでは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="50a94-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="50a94-127">通常、属性の宣言は、属性ターゲットの宣言の直前に記述されます。</span><span class="sxs-lookup"><span data-stu-id="50a94-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="50a94-128">複数の属性宣言は、次のように組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="50a94-128">Multiple attribute declarations can be used together, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="50a94-129">.NET リフレクションを使用すると、実行時に属性に対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="50a94-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="50a94-130">前のコード例のように、複数の属性を個別に宣言することも、セミコロンを使用して個々の属性とコンストラクターを区切る場合は、1組の角かっこで宣言することもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="50a94-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="50a94-131">通常、属性には、`Obsolete` 属性、セキュリティに関する考慮事項の属性、COM サポートの属性、コードの所有権に関連する属性、および型をシリアル化できるかどうかを示す属性があります。</span><span class="sxs-lookup"><span data-stu-id="50a94-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="50a94-132">次の例では、`Obsolete` 属性の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50a94-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="50a94-133">属性ターゲット `assembly` および `module`については、アセンブリ内の最上位 `do` バインディングに属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="50a94-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="50a94-134">次のように、属性の宣言に word `assembly` または `module` を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="50a94-134">You can include the word `assembly` or `module` in the attribute declaration, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="50a94-135">`do` バインディングに適用されている属性の属性ターゲットを省略したF#場合、コンパイラはその属性に対して意味のある属性ターゲットを特定しようとします。</span><span class="sxs-lookup"><span data-stu-id="50a94-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="50a94-136">多くの属性クラスには、その属性でサポートされているターゲットに関する情報を含む `System.AttributeUsageAttribute` 型の属性があります。</span><span class="sxs-lookup"><span data-stu-id="50a94-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="50a94-137">`System.AttributeUsageAttribute` が、属性がターゲットとしての関数をサポートしていることを示している場合、属性はプログラムのメインエントリポイントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="50a94-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="50a94-138">属性がターゲットとしてのアセンブリをサポートしていることが `System.AttributeUsageAttribute` によって示された場合、コンパイラは、アセンブリに適用する属性を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="50a94-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="50a94-139">ほとんどの属性は、関数とアセンブリの両方には適用されませんが、その場合、属性はプログラムの main 関数に適用されます。</span><span class="sxs-lookup"><span data-stu-id="50a94-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="50a94-140">属性ターゲットが明示的に指定されている場合は、指定されたターゲットに属性が適用されます。</span><span class="sxs-lookup"><span data-stu-id="50a94-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="50a94-141">通常、属性ターゲットを明示的に指定する必要はありませんが、次の表に示すように、属性の*target*に有効な値を使用例と共に示します。</span><span class="sxs-lookup"><span data-stu-id="50a94-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute along with examples of usage are shown in the following table:</span></span>

<table>
  <tr>
    <th><span data-ttu-id="50a94-142">属性のターゲット</span><span class="sxs-lookup"><span data-stu-id="50a94-142">Attribute target</span></span></td>
    <th><span data-ttu-id="50a94-143">例</span><span class="sxs-lookup"><span data-stu-id="50a94-143">Example</span></span></td>
  </tr>
  <tr>
    <td><span data-ttu-id="50a94-144">アセンブリ (assembly)</span><span class="sxs-lookup"><span data-stu-id="50a94-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="50a94-145">return</span><span class="sxs-lookup"><span data-stu-id="50a94-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="50a94-146">フィールド</span><span class="sxs-lookup"><span data-stu-id="50a94-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="50a94-147">property</span><span class="sxs-lookup"><span data-stu-id="50a94-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="50a94-148">param</span><span class="sxs-lookup"><span data-stu-id="50a94-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="50a94-149">型</span><span class="sxs-lookup"><span data-stu-id="50a94-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(LayoutKind.Sequential)&gt;]
type MyStruct =
  struct
    val x : byte
    val y : int
  end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="50a94-150">参照</span><span class="sxs-lookup"><span data-stu-id="50a94-150">See also</span></span>

- [<span data-ttu-id="50a94-151">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="50a94-151">F# Language Reference</span></span>](index.md)
