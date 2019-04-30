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
ms.openlocfilehash: 9a844515a4596064937762ac05b850463f1b5e14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051703"
---
# <a name="-filealign"></a><span data-ttu-id="841fe-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="841fe-102">-filealign</span></span>
<span data-ttu-id="841fe-103">出力ファイルでセクションをアラインするサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="841fe-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="841fe-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="841fe-105">引数</span><span class="sxs-lookup"><span data-stu-id="841fe-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="841fe-106">必須。</span><span class="sxs-lookup"><span data-stu-id="841fe-106">Required.</span></span> <span data-ttu-id="841fe-107">出力ファイルのセクションの配置を指定する値。</span><span class="sxs-lookup"><span data-stu-id="841fe-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="841fe-108">有効値は 512、1024、2048、4096、および 8192 です。</span><span class="sxs-lookup"><span data-stu-id="841fe-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="841fe-109">これらの値はバイト単位です。</span><span class="sxs-lookup"><span data-stu-id="841fe-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="841fe-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="841fe-110">Remarks</span></span>  
 <span data-ttu-id="841fe-111">使用することができます、`-filealign`出力ファイル内のセクションのアラインメントを指定するオプション。</span><span class="sxs-lookup"><span data-stu-id="841fe-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="841fe-112">セクションは、コードまたはデータを含むポータブル実行可能ファイル (PE) ファイルの連続したメモリのブロックです。</span><span class="sxs-lookup"><span data-stu-id="841fe-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="841fe-113">`-filealign`オプションを使用して、非標準の配置を使用してアプリケーションをコンパイルできます。 ほとんどの開発者は、このオプションを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="841fe-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="841fe-114">各セクションは整列の倍数である境界、`-filealign`値。</span><span class="sxs-lookup"><span data-stu-id="841fe-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="841fe-115">固定の既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="841fe-115">There is no fixed default.</span></span> <span data-ttu-id="841fe-116">場合`-filealign`が指定されていない、コンパイラがコンパイル時に、既定値を選択します。</span><span class="sxs-lookup"><span data-stu-id="841fe-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="841fe-117">セクションのサイズを指定すると、出力ファイルのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="841fe-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="841fe-118">セクションのサイズ変更は、比較的小さなデバイスで実行されるプログラムに対して有効な場合があります。</span><span class="sxs-lookup"><span data-stu-id="841fe-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="841fe-119">`-filealign`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="841fe-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841fe-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="841fe-120">See also</span></span>

- [<span data-ttu-id="841fe-121">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="841fe-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
