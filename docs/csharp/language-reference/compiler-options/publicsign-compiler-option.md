---
description: -publicsign (C# コンパイラ オプション)
title: -publicsign (C# コンパイラ オプション)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 525912c7f50aa6b51e602be7b9258f1f5907daac
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124813"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="df588-103">-publicsign (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="df588-103">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="df588-104">このオプションを指定すると、コンパイラは公開キーを適用しますが、実際にはアセンブリに署名しません。</span><span class="sxs-lookup"><span data-stu-id="df588-104">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="df588-105">**-publicsign** オプションは、ファイルが実際に署名されていることをランタイムに伝えるアセンブリのビットも設定します。</span><span class="sxs-lookup"><span data-stu-id="df588-105">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="df588-106">構文</span><span class="sxs-lookup"><span data-stu-id="df588-106">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="df588-107">引数</span><span class="sxs-lookup"><span data-stu-id="df588-107">Arguments</span></span>

<span data-ttu-id="df588-108">[なし] :</span><span class="sxs-lookup"><span data-stu-id="df588-108">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="df588-109">解説</span><span class="sxs-lookup"><span data-stu-id="df588-109">Remarks</span></span>

<span data-ttu-id="df588-110">**-publicsign** オプションを使うには、[-keyfile](keyfile-compiler-option.md) または [-keycontainer](keycontainer-compiler-option.md) を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="df588-110">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="df588-111">**keyfile** または **keycontainer** オプションは、公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="df588-111">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="df588-112">**-publicsign** オプションと **-delaysign** オプションは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="df588-112">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="df588-113">"フェイク署名" または "OSS 署名" と呼ばれることもあり、公開署名には出力アセンブリ内の公開キーが含まれ、"署名済み" フラグは設定されますが、実際には秘密キーによるアセンブリの署名は行われません。</span><span class="sxs-lookup"><span data-stu-id="df588-113">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="df588-114">これは、リリースされている "完全に署名された" アセンブリと互換性を持ちながら、アセンブリの署名に使われた秘密キーへはアクセスできない、そのようなアセンブリをビルドするオープン ソース プロジェクトに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df588-114">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="df588-115">アセンブリが完全に署名されているかどうかをコンシューマーが実際に確認する必要があることはほとんどないので、このようなパブリックにビルドされたアセンブリは、完全に署名されたアセンブリが使われるほとんどすべてのシナリオにおいて使用可能です。</span><span class="sxs-lookup"><span data-stu-id="df588-115">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a><span data-ttu-id="df588-116">csproj ファイルでこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="df588-116">To set this compiler option in a csproj file</span></span>

<span data-ttu-id="df588-117">プロジェクトの .csproj ファイルを開き、次の要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="df588-117">Open the .csproj file for a project, and add the following element:</span></span>

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a><span data-ttu-id="df588-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="df588-118">See also</span></span>

- [<span data-ttu-id="df588-119">C# コンパイラの -delaysign オプション</span><span class="sxs-lookup"><span data-stu-id="df588-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="df588-120">C# コンパイラの -keyfile オプション</span><span class="sxs-lookup"><span data-stu-id="df588-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="df588-121">C# コンパイラの -keycontainer オプション</span><span class="sxs-lookup"><span data-stu-id="df588-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="df588-122">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="df588-122">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="df588-123">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="df588-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
