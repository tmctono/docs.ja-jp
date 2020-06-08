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
ms.openlocfilehash: 3877757185030b0dba914a79d8c760fb8033ae5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408648"
---
# <a name="-filealign"></a><span data-ttu-id="ae7f0-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="ae7f0-102">-filealign</span></span>
<span data-ttu-id="ae7f0-103">出力ファイルでセクションをアラインするサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae7f0-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae7f0-105">引数</span><span class="sxs-lookup"><span data-stu-id="ae7f0-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="ae7f0-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-106">Required.</span></span> <span data-ttu-id="ae7f0-107">出力ファイルにセクションの配置を指定する値です。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="ae7f0-108">有効値は 512、1024、2048、4096、および 8192 です。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="ae7f0-109">これらの値はバイト単位です。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae7f0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae7f0-110">Remarks</span></span>  
 <span data-ttu-id="ae7f0-111">`-filealign` オプションは、ご自分の出力ファイルにセクションの配置を指定するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="ae7f0-112">セクションは、コードまたはデータのいずれかを含む、移植可能な実行可能 (PE) ファイルの連続したメモリのブロックです。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="ae7f0-113">`-filealign` オプションを使用すると、非標準の配置でご自分のアプリケーションをコンパイルできます。ほとんどの開発者は、このオプションを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="ae7f0-114">各セクションは、`-filealign` 値の倍数の境界上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="ae7f0-115">固定の既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-115">There is no fixed default.</span></span> <span data-ttu-id="ae7f0-116">`-filealign` を指定しない場合、コンパイル時にコンパイラによって既定が選択されます。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="ae7f0-117">セクションのサイズを指定すると、出力ファイルのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="ae7f0-118">セクションのサイズ変更は、比較的小さなデバイスで実行されるプログラムに対して有効な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae7f0-119">`-filealign` オプションは、Visual Studio 開発環境からは利用できません。これはコマンド ラインからコンパイルするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae7f0-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7f0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae7f0-120">See also</span></span>

- [<span data-ttu-id="ae7f0-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="ae7f0-121">Visual Basic Command-Line Compiler</span></span>](index.md)
