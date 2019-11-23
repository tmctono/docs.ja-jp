---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005588"
---
# <a name="-filealign"></a><span data-ttu-id="3fd6c-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="3fd6c-102">-filealign</span></span>
<span data-ttu-id="3fd6c-103">出力ファイルでセクションをアラインするサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="3fd6c-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="3fd6c-105">引数</span><span class="sxs-lookup"><span data-stu-id="3fd6c-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="3fd6c-106">必須。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-106">Required.</span></span> <span data-ttu-id="3fd6c-107">出力ファイル内のセクションの配置を指定する値。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="3fd6c-108">有効値は 512、1024、2048、4096、および 8192 です。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="3fd6c-109">これらの値はバイト単位です。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fd6c-110">コメント</span><span class="sxs-lookup"><span data-stu-id="3fd6c-110">Remarks</span></span>  
 <span data-ttu-id="3fd6c-111">`-filealign` オプションを使用して、出力ファイル内のセクションの配置を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="3fd6c-112">セクションは、コードまたはデータのいずれかを含む移植可能な実行可能 (PE) ファイル内の連続したメモリのブロックです。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="3fd6c-113">`-filealign` オプションを使用すると、非標準の配置でアプリケーションをコンパイルできます。ほとんどの開発者は、このオプションを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="3fd6c-114">各セクションは、`-filealign` 値の倍数である境界上にアラインされます。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="3fd6c-115">固定の既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-115">There is no fixed default.</span></span> <span data-ttu-id="3fd6c-116">`-filealign` が指定されていない場合、コンパイラはコンパイル時に既定値を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="3fd6c-117">セクションのサイズを指定することにより、出力ファイルのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="3fd6c-118">セクションのサイズ変更は、比較的小さなデバイスで実行されるプログラムに対して有効な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fd6c-119">`-filealign` オプションは、Visual Studio 開発環境内からは使用できません。これは、コマンドラインからコンパイルする場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fd6c-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd6c-120">参照</span><span class="sxs-lookup"><span data-stu-id="3fd6c-120">See also</span></span>

- [<span data-ttu-id="3fd6c-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="3fd6c-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
