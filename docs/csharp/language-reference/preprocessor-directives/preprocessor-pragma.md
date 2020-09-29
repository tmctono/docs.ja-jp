---
description: '#pragma - C# リファレンス'
title: '#pragma - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168518"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="3ccce-103">#pragma (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3ccce-103">#pragma (C# Reference)</span></span>

<span data-ttu-id="3ccce-104">`#pragma` は、ファイル内に指定され、そのファイルのコンパイルについての特別な命令をコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="3ccce-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="3ccce-105">命令はコンパイラによってサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccce-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="3ccce-106">つまり、`#pragma` を使用してカスタムの前処理命令を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ccce-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="3ccce-107">Microsoft C# コンパイラは、次の 2 つの `#pragma` 命令をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3ccce-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="3ccce-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3ccce-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="3ccce-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3ccce-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="3ccce-110">構文</span><span class="sxs-lookup"><span data-stu-id="3ccce-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ccce-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ccce-111">Parameters</span></span>  

 `pragma-name`  
 <span data-ttu-id="3ccce-112">認識されているプラグマの名前。</span><span class="sxs-lookup"><span data-stu-id="3ccce-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="3ccce-113">プラグマに固有の引数。</span><span class="sxs-lookup"><span data-stu-id="3ccce-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ccce-114">See also</span></span>

- [<span data-ttu-id="3ccce-115">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3ccce-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3ccce-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3ccce-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3ccce-117">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3ccce-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="3ccce-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3ccce-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="3ccce-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3ccce-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
