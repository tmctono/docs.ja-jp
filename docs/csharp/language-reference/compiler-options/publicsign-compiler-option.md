---
title: -publicsign (C# コンパイラ オプション)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: de7d9c98b0f279b52bc93711c5b986a2b2e57215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "61662531"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="f4065-102">-publicsign (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="f4065-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="f4065-103">このオプションを指定すると、コンパイラは公開キーを適用しますが、実際にはアセンブリに署名しません。</span><span class="sxs-lookup"><span data-stu-id="f4065-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="f4065-104">**-publicsign** オプションは、ファイルが実際に署名されていることをランタイムに伝えるアセンブリのビットも設定します。</span><span class="sxs-lookup"><span data-stu-id="f4065-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4065-105">構文</span><span class="sxs-lookup"><span data-stu-id="f4065-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="f4065-106">引数</span><span class="sxs-lookup"><span data-stu-id="f4065-106">Arguments</span></span>

<span data-ttu-id="f4065-107">[なし] :</span><span class="sxs-lookup"><span data-stu-id="f4065-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4065-108">解説</span><span class="sxs-lookup"><span data-stu-id="f4065-108">Remarks</span></span>

<span data-ttu-id="f4065-109">**-publicsign** オプションを使うには、[-keyfile](keyfile-compiler-option.md) または [-keycontainer](keycontainer-compiler-option.md) を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4065-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="f4065-110">**keyfile** または **keycontainer** オプションは、公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4065-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="f4065-111">**-publicsign** オプションと **-delaysign** オプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="f4065-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="f4065-112">"フェイク署名" または "OSS 署名" と呼ばれることもあり、公開署名には出力アセンブリ内の公開キーが含まれ、"署名済み" フラグは設定されますが、実際には秘密キーによるアセンブリの署名は行われません。</span><span class="sxs-lookup"><span data-stu-id="f4065-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="f4065-113">これは、リリースされている "完全に署名された" アセンブリと互換性を持ちながら、アセンブリの署名に使われた秘密キーへはアクセスできない、そのようなアセンブリをビルドするオープン ソース プロジェクトに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4065-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="f4065-114">アセンブリが完全に署名されているかどうかをコンシューマーが実際に確認する必要があることはほとんどないので、このようなパブリックにビルドされたアセンブリは、完全に署名されたアセンブリが使われるほとんどすべてのシナリオにおいて使用可能です。</span><span class="sxs-lookup"><span data-stu-id="f4065-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f4065-115">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="f4065-115">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="f4065-116">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4065-116">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="f4065-117">**[遅延署名のみ]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="f4065-117">Modify the **Delay sign only** property.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4065-118">参照</span><span class="sxs-lookup"><span data-stu-id="f4065-118">See also</span></span>

- [<span data-ttu-id="f4065-119">C# コンパイラの -delaysign オプション</span><span class="sxs-lookup"><span data-stu-id="f4065-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="f4065-120">C# コンパイラの -keyfile オプション</span><span class="sxs-lookup"><span data-stu-id="f4065-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="f4065-121">C# コンパイラの -keycontainer オプション</span><span class="sxs-lookup"><span data-stu-id="f4065-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="f4065-122">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="f4065-122">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="f4065-123">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="f4065-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
