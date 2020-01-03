---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: be2ad1416e801398fb513593c7f3828e5488bfaf
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005531"
---
# <a name="-keycontainer"></a><span data-ttu-id="49232-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="49232-102">-keycontainer</span></span>
<span data-ttu-id="49232-103">アセンブリに厳密な名前を付けるキー ペアのキー コンテナー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="49232-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49232-104">構文</span><span class="sxs-lookup"><span data-stu-id="49232-104">Syntax</span></span>  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="49232-105">引数</span><span class="sxs-lookup"><span data-stu-id="49232-105">Arguments</span></span>  
  
|<span data-ttu-id="49232-106">項目</span><span class="sxs-lookup"><span data-stu-id="49232-106">Term</span></span>|<span data-ttu-id="49232-107">定義</span><span class="sxs-lookup"><span data-stu-id="49232-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="49232-108">必須。</span><span class="sxs-lookup"><span data-stu-id="49232-108">Required.</span></span> <span data-ttu-id="49232-109">キーが格納されているコンテナーファイル。</span><span class="sxs-lookup"><span data-stu-id="49232-109">Container file that contains the key.</span></span> <span data-ttu-id="49232-110">名前にスペースが含まれている場合は、ファイル名を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="49232-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49232-111">コメント</span><span class="sxs-lookup"><span data-stu-id="49232-111">Remarks</span></span>  
 <span data-ttu-id="49232-112">コンパイラは公開キーをアセンブリマニフェストに挿入し、最後のアセンブリに秘密キーで署名することによって、共有可能なコンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="49232-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="49232-113">キー ファイルを生成するには、コマンド ラインで「`sn -k file`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="49232-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="49232-114">@No__t-0 オプションを指定すると、キーペアがコンテナーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="49232-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="49232-115">詳細については、「[sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49232-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="49232-116">@No__t-0 を指定してコンパイルすると、キーファイルの名前がモジュールに保持され、 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)を使用してアセンブリをコンパイルするときに作成されるアセンブリに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="49232-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="49232-117">このオプションは、任意の Microsoft Intermediate Language (MSIL) モジュールのソース コードで、カスタム属性 (<xref:System.Reflection.AssemblyKeyNameAttribute>) として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="49232-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="49232-118">また、暗号化情報を [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) でコンパイラに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="49232-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="49232-119">部分的に署名されたアセンブリを作成する場合は、[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) を使います。</span><span class="sxs-lookup"><span data-stu-id="49232-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="49232-120">アセンブリに署名する方法の詳細については、「[厳密な名前付きアセンブリの作成と使用](../../../standard/assembly/create-use-strong-named.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49232-120">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49232-121">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="49232-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49232-122">例</span><span class="sxs-lookup"><span data-stu-id="49232-122">Example</span></span>  
 <span data-ttu-id="49232-123">次のコードでは、ソースファイル `Input.vb` でコンパイルし、キーコンテナーを指定しています。</span><span class="sxs-lookup"><span data-stu-id="49232-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="49232-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="49232-124">See also</span></span>

- [<span data-ttu-id="49232-125">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="49232-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="49232-126">Visual Basic コマンドラインコンパイラ</span><span class="sxs-lookup"><span data-stu-id="49232-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="49232-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="49232-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="49232-128">コンパイルコマンドラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="49232-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
