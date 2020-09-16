---
title: 例外の種類
description: 'F # の例外の種類を定義して使用する方法について説明します。'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557230"
---
# <a name="exception-types"></a>例外の種類

F # には、.NET の例外の種類と F # の例外の種類という2つのカテゴリがあります。 このトピックでは、F # の例外の種類を定義して使用する方法について説明します。

## <a name="syntax"></a>構文

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Remarks

前の構文では、 *例外の種類* は新しい F # の例外の種類の名前で、引数の *型* は、この型の例外を発生させたときに指定できる引数の型を表します。 *引数の型*にタプル型を使用すると、複数の引数を指定できます。

F # 例外の一般的な定義は、次のようになります。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

この型の例外を生成するには、次のように関数を使用し `raise` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

次の例に示すように、式のフィルターで F # の例外の種類を直接使用でき `try...with` ます。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

F # でキーワードを使用して定義する例外の種類 `exception` は、から継承される新しい型です `System.Exception` 。

## <a name="see-also"></a>関連項目

- [例外処理](index.md)
- [例外: `raise` 関数](the-raise-function.md)
- [例外階層](../../../standard/exceptions/index.md)
