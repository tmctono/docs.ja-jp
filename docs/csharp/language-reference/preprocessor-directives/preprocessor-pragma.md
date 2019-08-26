---
title: '#pragma - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65ca38ff6993117b6ed9f716d4ac93ba2d4a9ddf
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605671"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="3bc9b-102">#pragma (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3bc9b-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="3bc9b-103">`#pragma` は、ファイル内に指定され、そのファイルのコンパイルについての特別な命令をコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="3bc9b-104">命令はコンパイラによってサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="3bc9b-105">つまり、`#pragma` を使用してカスタムの前処理命令を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="3bc9b-106">Microsoft C# コンパイラは、次の 2 つの `#pragma` 命令をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="3bc9b-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3bc9b-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="3bc9b-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3bc9b-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="3bc9b-109">構文</span><span class="sxs-lookup"><span data-stu-id="3bc9b-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bc9b-110">parameters</span><span class="sxs-lookup"><span data-stu-id="3bc9b-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="3bc9b-111">認識されているプラグマの名前。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="3bc9b-112">プラグマに固有の引数。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc9b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bc9b-113">See also</span></span>

- [<span data-ttu-id="3bc9b-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3bc9b-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3bc9b-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3bc9b-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3bc9b-116">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3bc9b-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="3bc9b-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3bc9b-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="3bc9b-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3bc9b-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
