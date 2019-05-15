---
title: 属性
description: 学習方法F#属性を使用するプログラミング コンストラクトに適用されるメタデータ。
ms.date: 05/16/2016
ms.openlocfilehash: fed4c549b95d6d3701ab81cf5d62add411c16038
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642022"
---
# <a name="attributes"></a><span data-ttu-id="97015-103">属性</span><span class="sxs-lookup"><span data-stu-id="97015-103">Attributes</span></span>

<span data-ttu-id="97015-104">属性は、プログラミング コンストラクトに適用されるメタデータを有効にします。</span><span class="sxs-lookup"><span data-stu-id="97015-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="97015-105">構文</span><span class="sxs-lookup"><span data-stu-id="97015-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="97015-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="97015-106">Remarks</span></span>

<span data-ttu-id="97015-107">前の構文で、*ターゲット*省略可能ですが、存在する場合は、属性が適用されるプログラム エンティティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="97015-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="97015-108">有効な値*ターゲット*このドキュメントの後半で表示されるテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="97015-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="97015-109">*属性名*サフィックスの有無で、有効な属性型の名前 (場合によっては名前空間を持つ修飾名) を指す`Attribute`属性の型名で通常使用されています。</span><span class="sxs-lookup"><span data-stu-id="97015-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="97015-110">たとえば、型`ObsoleteAttribute`だけに短縮できます`Obsolete`このコンテキストでします。</span><span class="sxs-lookup"><span data-stu-id="97015-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="97015-111">*引数*属性型のコンス トラクターへの引数です。</span><span class="sxs-lookup"><span data-stu-id="97015-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="97015-112">属性に既定のコンス トラクターがある場合は、引数リストとかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="97015-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="97015-113">属性は、位置指定引数と名前付き引数の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="97015-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="97015-114">*位置指定引数*が出現する順序で使用される引数。</span><span class="sxs-lookup"><span data-stu-id="97015-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="97015-115">属性は、パブリック プロパティを持つ場合、名前付き引数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="97015-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="97015-116">引数リストで、次の構文を使用して、これらを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="97015-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="97015-117">このようなプロパティの初期化は、任意の順序で指定できますが、位置引数に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="97015-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="97015-118">位置指定引数とプロパティの初期化を使用する属性の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="97015-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="97015-119">この例では、属性は`DllImportAttribute`、ここで短縮形で使用します。</span><span class="sxs-lookup"><span data-stu-id="97015-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="97015-120">最初の引数が位置指定パラメーターと、2 番目のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="97015-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="97015-121">属性は、.NET のプログラミング コンストラクトと呼ばれる、オブジェクトを有効にする、*属性*型またはその他のプログラム要素に関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="97015-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="97015-122">属性が適用されるプログラム要素と呼ばれる、*属性ターゲット*します。</span><span class="sxs-lookup"><span data-stu-id="97015-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="97015-123">属性には、通常は、ターゲットに関するメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="97015-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="97015-124">このコンテキストでは、メタデータは、フィールドやメンバー以外の種類に関するすべてのデータになります。</span><span class="sxs-lookup"><span data-stu-id="97015-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="97015-125">属性F#次のプログラミング構成要素に適用できます: 関数、メソッド、アセンブリ、モジュール、型 (クラス、レコード、構造体、インターフェイス、デリゲート、列挙体、共用体、およびなど)、コンス トラクター、プロパティ、フィールド、パラメーターは、入力パラメーター、および戻り値。</span><span class="sxs-lookup"><span data-stu-id="97015-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="97015-126">属性では許可されません`let`クラス、式、またはワークフローの式内でバインドします。</span><span class="sxs-lookup"><span data-stu-id="97015-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="97015-127">通常、属性の宣言は、属性ターゲット宣言の前に直接表示されます。</span><span class="sxs-lookup"><span data-stu-id="97015-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="97015-128">複数の属性宣言は、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="97015-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="97015-129">.NET リフレクションを使用して、実行時に属性を照会できます。</span><span class="sxs-lookup"><span data-stu-id="97015-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="97015-130">前のコード例のように複数の属性を個別に宣言または次に示すように個々 の属性と、コンス トラクターを分離する、セミコロンを使用する場合は、1 つの組の角かっこで宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="97015-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="97015-131">よく発生属性が含まれます、`Obsolete`属性、セキュリティの考慮事項は、属性は、COM サポート、コードの所有権に関連する属性および属性の型をシリアル化できるかどうかを示す属性です。</span><span class="sxs-lookup"><span data-stu-id="97015-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="97015-132">次の例では、使用、`Obsolete`属性。</span><span class="sxs-lookup"><span data-stu-id="97015-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="97015-133">属性の対象の`assembly`と`module`、最上位に属性を適用する`do`アセンブリにバインドします。</span><span class="sxs-lookup"><span data-stu-id="97015-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="97015-134">単語を含めることができます`assembly`または`module`属性の宣言で、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="97015-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="97015-135">適用する属性の属性のターゲットを省略したかどうか、 `do` 、バインド、その属性の意味のある属性のターゲットを特定しようと試みます F# コンパイラ。</span><span class="sxs-lookup"><span data-stu-id="97015-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="97015-136">多くの属性クラスは、型の属性を持つ`System.AttributeUsageAttribute`その属性のサポートされている対象に関する情報を含むです。</span><span class="sxs-lookup"><span data-stu-id="97015-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="97015-137">場合、`System.AttributeUsageAttribute`属性には、ターゲットとしての関数がサポートされています、プログラムのメイン エントリ ポイントに適用する属性が実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="97015-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="97015-138">場合、`System.AttributeUsageAttribute`属性は、ターゲットとしてのアセンブリをサポートしています、コンパイラがアセンブリに適用する属性を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="97015-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="97015-139">関数と、アセンブリの両方にほとんどの属性は適用されませんが、プログラムの main 関数に適用する場合で属性が取得されます。</span><span class="sxs-lookup"><span data-stu-id="97015-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="97015-140">属性ターゲットを明示的に指定した場合は、属性が指定したターゲットに適用されます。</span><span class="sxs-lookup"><span data-stu-id="97015-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="97015-141">属性が対象の有効な値で明示的に、通常指定する必要はありませんが*ターゲット*属性での使用状況の例と、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="97015-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="97015-142">属性ターゲット</span><span class="sxs-lookup"><span data-stu-id="97015-142">Attribute target</span></span></td>
    <th><span data-ttu-id="97015-143">例</span><span class="sxs-lookup"><span data-stu-id="97015-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="97015-144">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="97015-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="97015-145">return</span><span class="sxs-lookup"><span data-stu-id="97015-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="97015-146">フィールド</span><span class="sxs-lookup"><span data-stu-id="97015-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="97015-147">property</span><span class="sxs-lookup"><span data-stu-id="97015-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="97015-148">param</span><span class="sxs-lookup"><span data-stu-id="97015-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="97015-149">型</span><span class="sxs-lookup"><span data-stu-id="97015-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="97015-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="97015-150">See also</span></span>

- [<span data-ttu-id="97015-151">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="97015-151">F# Language Reference</span></span>](index.md)
