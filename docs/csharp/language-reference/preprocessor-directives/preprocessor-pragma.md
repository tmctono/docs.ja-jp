---
title: '#pragma - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712456"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="0c419-102">#pragma (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0c419-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="0c419-103">`#pragma` は、ファイル内に指定され、そのファイルのコンパイルについての特別な命令をコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="0c419-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="0c419-104">命令はコンパイラによってサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c419-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="0c419-105">つまり、`#pragma` を使用してカスタムの前処理命令を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c419-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="0c419-106">Microsoft C# コンパイラは、次の 2 つの `#pragma` 命令をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0c419-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="0c419-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="0c419-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="0c419-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="0c419-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="0c419-109">構文</span><span class="sxs-lookup"><span data-stu-id="0c419-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c419-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c419-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="0c419-111">認識されているプラグマの名前。</span><span class="sxs-lookup"><span data-stu-id="0c419-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="0c419-112">プラグマに固有の引数。</span><span class="sxs-lookup"><span data-stu-id="0c419-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c419-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c419-113">See also</span></span>

- [<span data-ttu-id="0c419-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0c419-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0c419-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0c419-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0c419-116">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="0c419-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="0c419-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="0c419-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="0c419-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="0c419-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
