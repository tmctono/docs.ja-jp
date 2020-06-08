---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408700"
---
# <a name="-delaysign"></a><span data-ttu-id="92ed2-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="92ed2-102">-delaysign</span></span>

<span data-ttu-id="92ed2-103">アセンブリに完全に署名するか、部分的に署名するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="92ed2-104">構文</span><span class="sxs-lookup"><span data-stu-id="92ed2-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="92ed2-105">引数</span><span class="sxs-lookup"><span data-stu-id="92ed2-105">Arguments</span></span>

<span data-ttu-id="92ed2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="92ed2-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="92ed2-107">任意。</span><span class="sxs-lookup"><span data-stu-id="92ed2-107">Optional.</span></span> <span data-ttu-id="92ed2-108">完全署名されたアセンブリを作成する場合は、`-delaysign-` を使用します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="92ed2-109">公開キーをアセンブリに配置し、署名済みハッシュ用に領域を予約する場合は、`-delaysign+` を使用します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="92ed2-110">既定値は、`-delaysign-` です。</span><span class="sxs-lookup"><span data-stu-id="92ed2-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="92ed2-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="92ed2-111">Remarks</span></span>

<span data-ttu-id="92ed2-112">`-delaysign` オプションは、[-keyfile](keyfile.md) または [-keycontainer](keycontainer.md) と共に使用しない場合、無効になります。</span><span class="sxs-lookup"><span data-stu-id="92ed2-112">The `-delaysign` option has no effect unless used with [-keyfile](keyfile.md) or [-keycontainer](keycontainer.md).</span></span>

<span data-ttu-id="92ed2-113">アセンブリに完全に署名するように指定すると、コンパイラはマニフェスト (アセンブリ メタデータ) を含むファイルをハッシュし、秘密キーでそのハッシュに署名します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="92ed2-114">結果として得られるデジタル署名は、マニフェストを含むファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="92ed2-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="92ed2-115">アセンブリを遅延署名に設定すると、コンパイラは署名の計算も格納も行いませんが、後で署名を追加できるようにファイルに領域を確保します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="92ed2-116">たとえば、`-delaysign+` を使用すると、組織の開発者は、テスト担当者がグローバル アセンブリ キャッシュに登録して使用できるアセンブリの署名なしのテスト バージョンを配布できます。</span><span class="sxs-lookup"><span data-stu-id="92ed2-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="92ed2-117">アセンブリの作業が完了すると、組織の秘密キーの担当者がアセンブリに完全に署名できるようになります。</span><span class="sxs-lookup"><span data-stu-id="92ed2-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="92ed2-118">このコンパートメント化により、すべての開発者がアセンブリを操作できるようになると同時に、組織の秘密キーを漏えいから保護します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="92ed2-119">アセンブリへの署名の詳細については、「[厳密な名前付きアセンブリの作成と使用](../../../standard/assembly/create-use-strong-named.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ed2-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="92ed2-120">Visual Studio 統合開発環境で -delaysign を設定するには</span><span class="sxs-lookup"><span data-stu-id="92ed2-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="92ed2-121">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="92ed2-122">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92ed2-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="92ed2-123">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="92ed2-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="92ed2-124">**[遅延署名のみ]** ボックスに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="92ed2-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="92ed2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="92ed2-125">See also</span></span>

- [<span data-ttu-id="92ed2-126">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="92ed2-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="92ed2-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="92ed2-127">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="92ed2-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="92ed2-128">-keycontainer</span></span>](keycontainer.md)
- [<span data-ttu-id="92ed2-129">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="92ed2-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
