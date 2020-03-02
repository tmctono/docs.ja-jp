---
title: C# プログラムの一般構造 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
ms.openlocfilehash: 4a2340c29527ac09ba53daee03e06420b269df56
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673343"
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="de95b-102">C# プログラムの一般構造 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="de95b-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="de95b-103">C# プログラムは、1 つ以上のファイルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="de95b-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="de95b-104">各ファイルには、0 個以上の名前空間を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="de95b-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="de95b-105">名前空間には、その他の名前空間以外に、クラス、構造体、インターフェイス、列挙型、デリゲートなどの型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="de95b-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="de95b-106">次に示すのは、これら要素をすべて含む C# プログラムのスケルトンです。</span><span class="sxs-lookup"><span data-stu-id="de95b-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/class2.cs#34)]  
  
## <a name="related-sections"></a><span data-ttu-id="de95b-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="de95b-107">Related Sections</span></span>  
 <span data-ttu-id="de95b-108">詳細情報</span><span class="sxs-lookup"><span data-stu-id="de95b-108">For more information:</span></span>  
  
- [<span data-ttu-id="de95b-109">クラス</span><span class="sxs-lookup"><span data-stu-id="de95b-109">Classes</span></span>](../classes-and-structs/classes.md)  
  
- [<span data-ttu-id="de95b-110">構造体</span><span class="sxs-lookup"><span data-stu-id="de95b-110">Structs</span></span>](../../language-reference/builtin-types/struct.md)  
  
- [<span data-ttu-id="de95b-111">名前空間</span><span class="sxs-lookup"><span data-stu-id="de95b-111">Namespaces</span></span>](../namespaces/index.md)  
  
- [<span data-ttu-id="de95b-112">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de95b-112">Interfaces</span></span>](../interfaces/index.md)  
  
- [<span data-ttu-id="de95b-113">デリゲート</span><span class="sxs-lookup"><span data-stu-id="de95b-113">Delegates</span></span>](../delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="de95b-114">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="de95b-114">C# Language Specification</span></span>  

<span data-ttu-id="de95b-115">詳細については、「[C# 言語の仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の「[基本概念](~/_csharplang/spec/basic-concepts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de95b-115">For more information, see [Basic concepts](~/_csharplang/spec/basic-concepts.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="de95b-116">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="de95b-116">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de95b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="de95b-117">See also</span></span>

- [<span data-ttu-id="de95b-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="de95b-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="de95b-119">インサイド C# プログラム</span><span class="sxs-lookup"><span data-stu-id="de95b-119">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="de95b-120">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="de95b-120">C# Reference</span></span>](../../language-reference/index.md)
