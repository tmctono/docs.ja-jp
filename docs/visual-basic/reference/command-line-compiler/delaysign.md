---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 3ee94df096b756be544964cfbbd405355e3f728f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581266"
---
# <a name="-delaysign"></a><span data-ttu-id="a97cb-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="a97cb-102">-delaysign</span></span>

<span data-ttu-id="a97cb-103">アセンブリに完全に署名するか、部分的に署名するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a97cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="a97cb-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="a97cb-105">引数</span><span class="sxs-lookup"><span data-stu-id="a97cb-105">Arguments</span></span>

<span data-ttu-id="a97cb-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a97cb-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="a97cb-107">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a97cb-107">Optional.</span></span> <span data-ttu-id="a97cb-108">完全署名されたアセンブリを作成する場合は、`-delaysign-` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="a97cb-109">公開キーをアセンブリに配置し、署名されたハッシュ用の領域を予約する場合は、`-delaysign+` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="a97cb-110">既定値は、 `-delaysign-`です。</span><span class="sxs-lookup"><span data-stu-id="a97cb-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a97cb-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a97cb-111">Remarks</span></span>

<span data-ttu-id="a97cb-112">@No__t_0 オプションは、 [-](../../../visual-basic/reference/command-line-compiler/keyfile.md)キーまたは[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)と共に使用しない限り、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="a97cb-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>

<span data-ttu-id="a97cb-113">アセンブリに完全に署名するように指定すると、コンパイラはマニフェスト (アセンブリ メタデータ) を含むファイルをハッシュし、秘密キーでそのハッシュに署名します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="a97cb-114">結果として得られるデジタル署名は、マニフェストを含むファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a97cb-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="a97cb-115">アセンブリが遅延署名されている場合、コンパイラは署名を計算して保存しませんが、後で署名を追加できるように、ファイルに領域を確保します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="a97cb-116">たとえば、`-delaysign+` を使用すると、組織の開発者は、テスト担当者がグローバルアセンブリキャッシュに登録して使用できるアセンブリの署名されていないテストバージョンを配布できます。</span><span class="sxs-lookup"><span data-stu-id="a97cb-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="a97cb-117">アセンブリの作業が完了すると、組織の秘密キーを担当するユーザーがアセンブリに完全に署名できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a97cb-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="a97cb-118">この compartmentalization は、すべての開発者がアセンブリを操作できるようにすると同時に、組織の秘密キーを漏えいから保護します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="a97cb-119">アセンブリに署名する方法の詳細については、「[厳密な名前付きアセンブリの作成と使用](../../../standard/assembly/create-use-strong-named.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a97cb-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="a97cb-120">Visual Studio 統合開発環境で-delaysign を設定するには</span><span class="sxs-lookup"><span data-stu-id="a97cb-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="a97cb-121">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a97cb-122">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a97cb-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="a97cb-123">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a97cb-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="a97cb-124">**[遅延署名のみ]** ボックスに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a97cb-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="a97cb-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a97cb-125">See also</span></span>

- [<span data-ttu-id="a97cb-126">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="a97cb-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a97cb-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="a97cb-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="a97cb-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="a97cb-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="a97cb-129">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="a97cb-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
