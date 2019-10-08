---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 5b26e36346858d95526f5d5ce7d4645bea1dbe05
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005480"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="ae518-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="ae518-102">-moduleassemblyname</span></span>
<span data-ttu-id="ae518-103">このモジュールが一部となるアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae518-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae518-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae518-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae518-105">引数</span><span class="sxs-lookup"><span data-stu-id="ae518-105">Arguments</span></span>  
  
|<span data-ttu-id="ae518-106">項目</span><span class="sxs-lookup"><span data-stu-id="ae518-106">Term</span></span>|<span data-ttu-id="ae518-107">定義</span><span class="sxs-lookup"><span data-stu-id="ae518-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="ae518-108">このモジュールが含まれるアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="ae518-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae518-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ae518-109">Remarks</span></span>  
 <span data-ttu-id="ae518-110">コンパイラは、`-target:module` オプションが指定されている場合にのみ、`-moduleassemblyname` オプションを処理します。</span><span class="sxs-lookup"><span data-stu-id="ae518-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="ae518-111">これにより、コンパイラによってモジュールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ae518-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="ae518-112">コンパイラによって作成されたモジュールは、`-moduleassemblyname` オプションで指定されたアセンブリに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ae518-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="ae518-113">モジュールを別のアセンブリに配置すると、実行時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ae518-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="ae518-114">@No__t-0 オプションは、次の条件に該当する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ae518-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="ae518-115">モジュール内のデータ型は、参照されたアセンブリの @no__t 0 型にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae518-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="ae518-116">参照アセンブリは、モジュールがビルドされるアセンブリへのフレンドアセンブリアクセスを許可されています。</span><span class="sxs-lookup"><span data-stu-id="ae518-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="ae518-117">モジュールの作成の詳細については、「 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae518-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="ae518-118">フレンドアセンブリの詳細については、「[フレンドアセンブリ](../../../standard/assembly/friend.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae518-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae518-119">@No__t-0 オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドプロンプトからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae518-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae518-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae518-120">See also</span></span>

- [<span data-ttu-id="ae518-121">2 つのオブジェクトが等しいかどうかをテストする方法マルチファイル アセンブリをビルドする</span><span class="sxs-lookup"><span data-stu-id="ae518-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="ae518-122">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ae518-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ae518-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae518-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="ae518-124">-main</span><span class="sxs-lookup"><span data-stu-id="ae518-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="ae518-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae518-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="ae518-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="ae518-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="ae518-127">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="ae518-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="ae518-128">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="ae518-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ae518-129">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ae518-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
