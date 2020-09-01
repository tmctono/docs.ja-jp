---
description: -preferreduilang (C# コンパイラ オプション)
title: -preferreduilang (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: f68652e910651ab5c4184376d9eb7729303382d9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124852"
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang (C# コンパイラ オプション)
`-preferreduilang` コンパイラ オプションを使うと、C# コンパイラがエラー メッセージなどの出力を表示する言語を指定できます。  
  
## <a name="syntax"></a>構文  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>引数  
 `language`  
 コンパイラの出力に使う言語の[言語名](/windows/desktop/Intl/language-names)。  
  
## <a name="remarks"></a>注釈  
 `-preferreduilang` コンパイラ オプションを使うと、C# コンパイラがエラー メッセージおよびその他のコマンドライン出力に使う言語を指定できます。 言語の言語パックがインストールされていない場合は、オペレーティング システムの言語設定が代わりに使われ、エラーは報告されません。  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>必要条件  
  
## <a name="see-also"></a>関連項目

- [C# コンパイラ オプション](./index.md)
