---
title: let 束縛
description: "識別子を値または関数に関連付ける F # ' let ' バインドの使用方法について説明します。"
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812225"
---
# <a name="let-bindings"></a>let 束縛

*バインド*は、識別子を値または関数に関連付けます。 キーワードを使用して、 `let` 名前を値または関数にバインドします。

## <a name="syntax"></a>構文

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>解説

キーワードは、 `let` 1 つまたは複数の名前の値または関数の値を定義するために、バインド式で使用されます。 式の最も単純な形式は、次のよう `let` に単純な値に名前をバインドします。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

新しい行を使用して識別子から式を分離する場合は、次のコードのように、式の各行をインデントする必要があります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

次のコードに示すように、名前だけでなく、名前を含むパターンを指定することもできます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

*本体式*は、名前が使用される式です。 本文の式は、キーワード内の最初の文字と正確に一致する行にインデントされてい `let` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

バインディングは、 `let` モジュールレベル、クラス型の定義、またはローカルスコープ (関数定義など) で表示できます。 `let`モジュール内の最上位レベルまたはクラス型のバインディングは、本体式を持つ必要はありませんが、その他のスコープレベルでは、本体式が必要です。 バインドされた名前は、次のコードに示すように、定義の時点より後で使用できますが、バインドが表示される前の時点では使用できません `let` 。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>関数のバインド

関数のバインドは、次のコードに示すように、関数のバインドに関数名とパラメーターが含まれている点を除いて、値のバインドの規則に従います。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

一般に、パラメーターはタプルパターンなどのパターンです。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

`let`バインド式は、最後の式の値に評価されます。 したがって、次のコード例では、の値 `result` はに評価されるから計算され `100 * function3 (1, 2)` `300` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

詳細については、「[関数](index.md)」を参照してください。

## <a name="type-annotations"></a>型の注釈

パラメーターの型は、コロン (:) を含めることによって指定できます。の後に型名が続き、すべてがかっこで囲まれています。 戻り値の型を指定するには、最後のパラメーターの後にコロンと型を追加します。 `function1`パラメーターの型として整数を持つの完全な型の注釈は、次のようになります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

明示的な型パラメーターがない場合は、型の推定を使用して、関数のパラメーターの型を決定します。 これには、ジェネリックにするパラメーターの型を自動的に一般化することが含まれます。

詳細については、「 [自動汎](../generics/automatic-generalization.md) 化と [型推論](../type-inference.md)」を参照してください。

## <a name="let-bindings-in-classes"></a>クラス内の let 束縛

`let`バインドはクラス型では表示できますが、構造体またはレコード型では使用できません。 クラス型で let バインドを使用するには、クラスにプライマリコンストラクターが必要です。 コンストラクターのパラメーターは、クラス定義の型名の後に記述する必要があります。 `let`クラス型のバインディングは、そのクラス型のプライベートフィールドとメンバーを定義し、型のバインディングと共に、 `do` 型のプライマリコンストラクターのコードを形成します。 次のコード例は、プライベートフィールドとを持つクラスを示して `MyClass` `field1` `field2` います。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

とのスコープ `field1` は、宣言されている `field2` 型に制限されます。 詳細については、「クラスおよび[クラス](../classes.md) [ `let` のバインド](../members/let-bindings-in-classes.md)」を参照してください。

## <a name="type-parameters-in-let-bindings"></a>Let バインドの型パラメーター

`let`モジュールレベル、型、またはコンピュテーション式内のバインディングは、明示的な型パラメーターを持つことができます。 関数定義内などの式で let バインドを使用する場合、型パラメーターを指定することはできません。 詳細については、「[ジェネリック](../generics/index.md)」を参照してください。

## <a name="attributes-on-let-bindings"></a>Let バインドの属性

属性は、 `let` 次のコードに示すように、モジュールの最上位のバインドに適用できます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Let バインドのスコープとアクセシビリティ

Let バインドを使用して宣言されたエンティティのスコープは、バインドが表示された後に、コンテナースコープ (関数、モジュール、ファイル、クラスなど) の部分に限定されます。 そのため、let バインドによって名前がスコープに導入されることがあります。 モジュールでは、モジュール内の let バインドがモジュールのパブリック関数にコンパイルされるので、モジュールがアクセス可能であればモジュールのクライアントが使用できるようになります。 これに対して、クラス内のバインディングはクラスに対してプライベートです。

通常、モジュール内の関数は、クライアントコードで使用するときに、モジュールの名前で修飾する必要があります。 たとえば、モジュールに `Module1` 関数がある場合、 `function1` ユーザーは `Module1.function1` 関数を参照するように指定します。

モジュールのユーザーは、インポート宣言を使用して、モジュール名で修飾されていなくても、そのモジュール内の関数を使用できるようにすることができます。 前述の例では、モジュールのユーザーはインポート宣言を使用してモジュールを開くことができ、その `Module1` 後は直接を参照し `function1` ます。

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

一部のモジュールには [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)属性があります。つまり、公開する関数がモジュールの名前で修飾されている必要があります。 たとえば、F # リストモジュールにはこの属性があります。

モジュールとアクセス制御の詳細については、「 [モジュール](../modules.md) と [Access Control](../access-control.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [関数](index.md)
- [`let` クラス内のバインディング](../members/let-bindings-in-classes.md)
