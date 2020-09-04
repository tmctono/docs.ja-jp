---
title: LINQ クエリのカスタム メソッドを追加する方法 (C#)
description: C# で IEnumerable<T> インターフェイスに拡張メソッドを追加することで、LINQ クエリの構文を拡張する方法について学習します。
ms.date: 08/26/2020
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: 768882fce40a2fc6e018f24c8928341e7c65bc4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122427"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>LINQ クエリのカスタム メソッドを追加する方法 (C#)

<xref:System.Collections.Generic.IEnumerable%601> インターフェイスに拡張メソッドを追加することで、LINQ クエリに使用するメソッド セットを拡張します。 たとえば、一連の値から単一の値を計算するために、平均や最大を求める標準的な演算に加えて、カスタムの集計メソッドを作成します。 また、一連の値を受け取って新しい一連の値を返す特定のデータ変換やカスタム フィルターとして動作するメソッドも作成します。 このようなメソッドには、<xref:System.Linq.Enumerable.Distinct%2A>、<xref:System.Linq.Enumerable.Skip%2A>、<xref:System.Linq.Enumerable.Reverse%2A> があります。

<xref:System.Collections.Generic.IEnumerable%601> インターフェイスを拡張すると、列挙可能なコレクションにカスタム メソッドを適用できます。 詳細については、「[拡張メソッド](../../classes-and-structs/extension-methods.md)」を参照してください。

## <a name="adding-an-aggregate-method"></a>集計メソッドを追加する

集計メソッドは、一連の値から単一の値を計算するメソッドです。 LINQ は、<xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Min%2A>、<xref:System.Linq.Enumerable.Max%2A> などの集計メソッドを提供します。 <xref:System.Collections.Generic.IEnumerable%601> インターフェイスに拡張メソッドを追加することで、独自の集計メソッドを作成できます。

次のコード例は、`double` 型の一連の数値から中央値を求める `Median` という拡張メソッドの作成方法を示しています。

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="LinqExtensionClass":::

この拡張メソッドは、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスにある他の集計メソッドを呼び出すときと同じように、列挙可能な任意のコレクションに対して呼び出すことができます。

`double` 型の配列に対して `Median` メソッドを使用する方法を次のコード例に示します。

:::code language="csharp" source="./snippets/Program.cs" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>さまざまな型を受け取るために集計メソッドをオーバーロードする

集計メソッドでさまざまな型を受け取るように、集計メソッドをオーバーロードすることができます。 その標準的な方法として、型ごとにオーバーロードを作成します。 または、ジェネリック型を受け取り、デリゲートを使って特定の型に変換するオーバーロードを作成する方法もあります。 その両方の方法を組み合わせることもできます。

#### <a name="to-create-an-overload-for-each-type"></a>型ごとにオーバーロードを作成するには

サポート予定の型ごとに固有のオーバーロードを作成できます。 次のコード例では、`int` 型の `Median` メソッドのオーバーロードを示します。

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="IntOverload":::

これで、次のコードに示すように、`integer` 型と `double` 型の両方に対して、`Median` のオーバーロードを呼び出すことができるようになりました。

:::code language="csharp" source="./snippets/Program.cs" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a>ジェネリック オーバーロードを作成するには

一連のジェネリック オブジェクトを受け取るオーバーロードを作成することもできます。 このオーバーロードは、デリゲートをパラメーターとして受け取り、ジェネリック型の一連のオブジェクトを特定の型に変換します。

次のコードは、<xref:System.Func%602> デリゲートをパラメーターとして受け取る `Median` メソッドのオーバーロードを示しています。 このデリゲートは、ジェネリック型 T のオブジェクトを受け取り、`double` 型のオブジェクトを返します。

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="GenericOverload":::

これで、任意の型の一連のオブジェクトに対して `Median` メソッドを呼び出すことができます。 型に固有のメソッド オーバーロードがない場合は、デリゲート パラメーターを渡す必要があります。 この目的で、C# ではラムダ式を使用できます。 また、Visual Basic に限り、メソッド呼び出しの代わりに `Aggregate` 句または `Group By` 句を使用した場合、その句のスコープにある任意の値または式を渡すことができます。

次のコード例では、整数の配列と文字列の配列に対して `Median` メソッドを呼び出す方法を示します。 文字列の場合は、配列に格納されている文字列の長さの中央値が計算されます。 この例は、それぞれのケースについて、`Median` メソッドに <xref:System.Func%602> デリゲート パラメーターを渡す方法を示しています。

:::code language="csharp" source="./snippets/Program.cs" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-sequence"></a>シーケンスを返すメソッドを追加する

<xref:System.Collections.Generic.IEnumerable%601> インターフェイスは、一連の値を返すカスタム クエリ メソッドを追加することで拡張できます。 その場合、メソッドで型 <xref:System.Collections.Generic.IEnumerable%601> のコレクションを返す必要があります。 このようなメソッドを使用すると、一連の値にフィルターまたはデータ変換を適用することができます。

次の例では、コレクション内の最初の要素から 1 つおきに要素を返す `AlternateElements` という名前の拡張メソッドを作成する方法を示しています。

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="SequenceElement":::

この拡張メソッドは、次のコードに示すとおり、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスにある他のメソッドを呼び出すときと同じように、列挙可能な任意のコレクションに対して呼び出すことができます。

:::code language="csharp" source="./snippets/Program.cs" ID="SequenceUsage":::

## <a name="see-also"></a>関連項目

- <xref:System.Collections.Generic.IEnumerable%601>
- [拡張メソッド](../../classes-and-structs/extension-methods.md)
