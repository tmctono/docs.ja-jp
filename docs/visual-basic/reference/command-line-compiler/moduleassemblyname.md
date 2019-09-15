---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: dc4c0336c8a67a1b4e70f71ba5f5406da1fbb2ff
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972374"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="2a98c-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="2a98c-102">-moduleassemblyname</span></span>
<span data-ttu-id="2a98c-103">このモジュールが一部となるアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a98c-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a98c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a98c-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a98c-105">引数</span><span class="sxs-lookup"><span data-stu-id="2a98c-105">Arguments</span></span>  
  
|<span data-ttu-id="2a98c-106">用語</span><span class="sxs-lookup"><span data-stu-id="2a98c-106">Term</span></span>|<span data-ttu-id="2a98c-107">定義</span><span class="sxs-lookup"><span data-stu-id="2a98c-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="2a98c-108">このモジュールが含まれるアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="2a98c-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a98c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a98c-109">Remarks</span></span>  
 <span data-ttu-id="2a98c-110">オプションが指定さ`-moduleassemblyname`れて`-target:module`いる場合にのみ、コンパイラはオプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="2a98c-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="2a98c-111">これにより、コンパイラによってモジュールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2a98c-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="2a98c-112">コンパイラによって作成されたモジュールは、 `-moduleassemblyname`オプションで指定されたアセンブリに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="2a98c-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="2a98c-113">モジュールを別のアセンブリに配置すると、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2a98c-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="2a98c-114">`-moduleassemblyname`オプションは、次の条件に該当する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="2a98c-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="2a98c-115">モジュール内のデータ型は、参照され`Friend`たアセンブリの型にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a98c-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="2a98c-116">参照アセンブリは、モジュールがビルドされるアセンブリへのフレンドアセンブリアクセスを許可されています。</span><span class="sxs-lookup"><span data-stu-id="2a98c-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="2a98c-117">モジュールの作成の詳細については、「 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a98c-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="2a98c-118">フレンドアセンブリの詳細については、「[フレンドアセンブリ](../../../standard/assembly/friend.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a98c-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a98c-119">この`-moduleassemblyname`オプションは、Visual Studio 開発環境内からは使用できません。コマンドプロンプトからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a98c-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a98c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a98c-120">See also</span></span>

- [<span data-ttu-id="2a98c-121">方法: マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="2a98c-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="2a98c-122">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2a98c-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2a98c-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a98c-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2a98c-124">-main</span><span class="sxs-lookup"><span data-stu-id="2a98c-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="2a98c-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a98c-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="2a98c-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="2a98c-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="2a98c-127">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="2a98c-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="2a98c-128">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="2a98c-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2a98c-129">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="2a98c-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
