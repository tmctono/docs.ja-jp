---
description: protected キーワード - C# リファレンス
title: protected キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: af0c7ab5ebb6980bb0381e46fd38e9470f3a2152
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536757"
---
# <a name="protected-c-reference"></a>protected (C# リファレンス)

`protected` キーワードはメンバー アクセス修飾子です。

 > このページでは、`protected` アクセスについて説明します。 `protected` キーワードもアクセス修飾子の [`protected internal`](protected-internal.md) と [`private protected`](private-protected.md) に含まれます。

protected メンバーは、そのクラス内部と、派生クラスのインスタンスからアクセスできます。

`protected` と他のアクセス修飾子の比較については、「[アクセシビリティ レベル](accessibility-levels.md)」を参照してください。

## <a name="example"></a>例

派生クラス内で基底クラスの protected メンバーにアクセスできるのは、派生クラスの型を通してアクセスした場合のみです。 たとえば、次のコード セグメントを考えてみます。

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

ステートメント `a.x = 10` でエラーが発生します。これは、クラス B のインスタンスではなく、静的メソッド Main 内にあるためです。

構造体は継承できないため、構造体のメンバーを protected にすることはできません。

## <a name="example"></a>例

この例では、`DerivedPoint` クラスは `Point` から派生しています。 そのため、基底クラスの protected メンバーに、派生クラスから直接アクセスできます。

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

`x` と `y` のアクセス レベルを [private](private.md) に変更すると、コンパイラによってエラー メッセージが生成されます。

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a>C# 言語仕様  

詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[宣言されたアクセシビリティ](~/_csharplang/spec/basic-concepts.md#declared-accessibility)に関するセクションを参照してください。 言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# のキーワード](index.md)
- [アクセス修飾子](access-modifiers.md)
- [アクセシビリティ レベル](accessibility-levels.md)
- [修飾子](index.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Internal Virtual キーワードのセキュリティ関連事項](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
