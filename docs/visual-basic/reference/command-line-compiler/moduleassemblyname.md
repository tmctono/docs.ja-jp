---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 052d6937846df39bd94d532e1b63ebe522dbf6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964675"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="32d66-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="32d66-102">-moduleassemblyname</span></span>
<span data-ttu-id="32d66-103">このモジュールが一部となるアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="32d66-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d66-104">構文</span><span class="sxs-lookup"><span data-stu-id="32d66-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="32d66-105">引数</span><span class="sxs-lookup"><span data-stu-id="32d66-105">Arguments</span></span>  
  
|<span data-ttu-id="32d66-106">用語</span><span class="sxs-lookup"><span data-stu-id="32d66-106">Term</span></span>|<span data-ttu-id="32d66-107">定義</span><span class="sxs-lookup"><span data-stu-id="32d66-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="32d66-108">このモジュールが含まれるアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="32d66-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d66-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="32d66-109">Remarks</span></span>  
 <span data-ttu-id="32d66-110">オプションが指定さ`-moduleassemblyname`れて`-target:module`いる場合にのみ、コンパイラはオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="32d66-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="32d66-111">これにより、コンパイラによってモジュールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="32d66-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="32d66-112">コンパイラによって作成されたモジュールは、 `-moduleassemblyname`オプションで指定されたアセンブリに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="32d66-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="32d66-113">モジュールを別のアセンブリに配置すると、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="32d66-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="32d66-114">`-moduleassemblyname`オプションは、次の条件に該当する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="32d66-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="32d66-115">モジュール内のデータ型は、参照され`Friend`たアセンブリの型にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d66-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="32d66-116">参照アセンブリは、モジュールがビルドされるアセンブリへのフレンドアセンブリアクセスを許可されています。</span><span class="sxs-lookup"><span data-stu-id="32d66-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="32d66-117">モジュールの作成の詳細については、「 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d66-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="32d66-118">フレンドアセンブリの詳細については、「[フレンドアセンブリ](../../../standard/assembly/friend-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d66-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32d66-119">この`-moduleassemblyname`オプションは、Visual Studio 開発環境内からは使用できません。コマンドプロンプトからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="32d66-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d66-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="32d66-120">See also</span></span>

- [<span data-ttu-id="32d66-121">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="32d66-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="32d66-122">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="32d66-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="32d66-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32d66-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="32d66-124">-main</span><span class="sxs-lookup"><span data-stu-id="32d66-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="32d66-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32d66-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="32d66-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="32d66-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="32d66-127">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="32d66-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="32d66-128">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="32d66-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="32d66-129">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32d66-129">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
