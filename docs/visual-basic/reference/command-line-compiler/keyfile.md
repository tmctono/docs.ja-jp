---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 2617c42d7b176806cfac0fc2247760727608261a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775641"
---
# <a name="-keyfile"></a><span data-ttu-id="1910e-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="1910e-102">-keyfile</span></span>
<span data-ttu-id="1910e-103">アセンブリに厳密な名前を付けるキーまたはキー ペアを含むファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1910e-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1910e-104">構文</span><span class="sxs-lookup"><span data-stu-id="1910e-104">Syntax</span></span>  
  
```console 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="1910e-105">引数</span><span class="sxs-lookup"><span data-stu-id="1910e-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="1910e-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="1910e-106">Required.</span></span> <span data-ttu-id="1910e-107">キーを含むファイル。</span><span class="sxs-lookup"><span data-stu-id="1910e-107">File that contains the key.</span></span> <span data-ttu-id="1910e-108">ファイル名にスペースが含まれている場合は、名前を引用符 ("") で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1910e-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1910e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1910e-109">Remarks</span></span>  
 <span data-ttu-id="1910e-110">コンパイラは公開キーをアセンブリマニフェストに挿入し、秘密キーを使用して最終的なアセンブリに署名します。</span><span class="sxs-lookup"><span data-stu-id="1910e-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="1910e-111">キー ファイルを生成するには、コマンド ラインで「`sn -k file`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1910e-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="1910e-112">詳細については、「[sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1910e-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="1910e-113">@No__t_0 を指定してコンパイルすると、キーファイルの名前がモジュールに保持され、 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)を使用してアセンブリをコンパイルするときに作成されるアセンブリに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1910e-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="1910e-114">また、暗号化情報を [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) でコンパイラに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1910e-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="1910e-115">部分的に署名されたアセンブリを作成する場合は、[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) を使います。</span><span class="sxs-lookup"><span data-stu-id="1910e-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="1910e-116">このオプションは、Microsoft 中間言語モジュールのソースコードでカスタム属性 (<xref:System.Reflection.AssemblyKeyFileAttribute>) として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1910e-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="1910e-117">同じコンパイルで (コマンドラインオプションまたはカスタム属性によって) `-keyfile` と[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)の両方が指定されている場合、コンパイラは最初にキーコンテナーを試行します。</span><span class="sxs-lookup"><span data-stu-id="1910e-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="1910e-118">それが成功すると、アセンブリはキー コンテナーの情報で署名されます。</span><span class="sxs-lookup"><span data-stu-id="1910e-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="1910e-119">キーコンテナーが見つからない場合、コンパイラは `-keyfile` で指定されたファイルを試行します。</span><span class="sxs-lookup"><span data-stu-id="1910e-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="1910e-120">これが成功した場合、アセンブリはキーファイルの情報で署名され、キー情報はキーコンテナーにインストールされ (`sn -i` と同様)、次のコンパイル時にキーコンテナーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="1910e-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="1910e-121">キー ファイルには公開キーだけが含まれる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1910e-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="1910e-122">アセンブリに署名する方法の詳細については、「[厳密な名前付きアセンブリの作成と使用](../../../standard/assembly/create-use-strong-named.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1910e-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1910e-123">@No__t_0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1910e-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="1910e-124">例</span><span class="sxs-lookup"><span data-stu-id="1910e-124">Example</span></span>

<span data-ttu-id="1910e-125">次のコードでは、ソースファイル `Input.vb` をコンパイルし、キーファイルを指定しています。</span><span class="sxs-lookup"><span data-stu-id="1910e-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="1910e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1910e-126">See also</span></span>

- [<span data-ttu-id="1910e-127">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="1910e-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="1910e-128">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="1910e-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1910e-129">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1910e-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="1910e-130">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="1910e-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
