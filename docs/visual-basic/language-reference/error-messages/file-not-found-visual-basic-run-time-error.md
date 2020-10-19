---
title: ファイルが見つかりません。(Visual Basic ランタイム エラー)
ms.date: 07/20/2015
f1_keywords:
- vbrID53
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
ms.openlocfilehash: 6c65ca7f41af48f9fc8e60634815be1a615c561b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160725"
---
# <a name="file-not-found-visual-basic-run-time-error"></a>ファイルが見つかりません。(Visual Basic ランタイム エラー)

指定された場所でファイルが見つかりませんでした。 このエラーには、次のような原因が考えられます。

- ステートメントが、存在しないファイルを参照しています。

- ダイナミック リンク ライブラリ (DLL) でプロシージャを呼び出そうとしましたが、`Declare` ステートメントの `Lib` 句で指定されたライブラリが見つかりませんでした。

- プロジェクトを開こうとしたか、存在しないテキスト ファイルを読み込もうとしました。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- ファイル名とパスの指定のスペルを確認してください。

## <a name="see-also"></a>関連項目

- [Declare ステートメント](../statements/declare-statement.md)
