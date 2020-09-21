---
title: 例外の相互運用性
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 90774b5d1b64feb34e01f48708d94f8f841a7c9d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550873"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>アンマネージド コードでの相互運用例外の処理

アンマネージド コードの例外の相互運用は、Windows プラットフォームでのみサポートされています。 Windows 以外のプラットフォームでは移植性の問題が発生します。 Unix ABI には例外処理の定義がないため、マネージド コードでは、内部での例外メカニズムのしくみが認識されません。 そのため、例外が発生すると、予期しない動作やクラッシュが発生する可能性があります。

## <a name="setjmplongjmp-behaviors"></a>Setjmp と Longjmp の動作

`setjmp` および `longjmp` C 関数との相互運用はサポートされていません。 `longjmp` を使用して、マネージド フレームをスキップすることはできません。

詳しくは、[longjmp のドキュメント](/cpp/c-runtime-library/reference/longjmp)を参照してください。

## <a name="see-also"></a>関連項目

- [例外](index.md)
- [ネイティブ ライブラリとの相互運用](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
