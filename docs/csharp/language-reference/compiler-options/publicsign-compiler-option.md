---
title: -publicsign (C# コンパイラ オプション)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 2655e0216a412053e052ab2ec2fcc8c68ea4f968
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268050"
---
# <a name="-publicsign-c-compiler-options"></a>-publicsign (C# コンパイラ オプション)

このオプションを指定すると、コンパイラは公開キーを適用しますが、実際にはアセンブリに署名しません。 **-publicsign** オプションは、ファイルが実際に署名されていることをランタイムに伝えるアセンブリのビットも設定します。

## <a name="syntax"></a>構文

```console
-publicsign
```

## <a name="arguments"></a>引数

[なし] :

## <a name="remarks"></a>解説

**-publicsign** オプションを使うには、[-keyfile](keyfile-compiler-option.md) または [-keycontainer](keycontainer-compiler-option.md) を使う必要があります。 **keyfile** または **keycontainer** オプションは、公開キーを指定します。

**-publicsign** オプションと **-delaysign** オプションは相互に排他的です。

"フェイク署名" または "OSS 署名" と呼ばれることもあり、公開署名には出力アセンブリ内の公開キーが含まれ、"署名済み" フラグは設定されますが、実際には秘密キーによるアセンブリの署名は行われません。 これは、リリースされている "完全に署名された" アセンブリと互換性を持ちながら、アセンブリの署名に使われた秘密キーへはアクセスできない、そのようなアセンブリをビルドするオープン ソース プロジェクトに役立ちます。 アセンブリが完全に署名されているかどうかをコンシューマーが実際に確認する必要があることはほとんどないので、このようなパブリックにビルドされたアセンブリは、完全に署名されたアセンブリが使われるほとんどすべてのシナリオにおいて使用可能です。

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a>csproj ファイルでこのコンパイラ オプションを設定するには

プロジェクトの .csproj ファイルを開き、次の要素を追加します。

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a>関連項目

- [C# コンパイラの -delaysign オプション](delaysign-compiler-option.md)
- [C# コンパイラの -keyfile オプション](keyfile-compiler-option.md)
- [C# コンパイラの -keycontainer オプション](keycontainer-compiler-option.md)
- [C# コンパイラ オプション](index.md)
- [プロジェクトおよびソリューションのプロパティの管理](/visualstudio/ide/managing-project-and-solution-properties)
