---
title: 相互運用性 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 50f2a72bf4981a49d5597a9bc8922db81197d810
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710226"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="573dc-102">相互運用性 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="573dc-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="573dc-103">相互運用性は、アンマネージ コードへの既存の投資を保持して活用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="573dc-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="573dc-104">共通言語ランタイム (CLR) の制御下で実行されるコードは*マネージド コード*と呼ばれ、CLR の外部で実行されるコードは*アンマネージド コード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="573dc-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="573dc-105">アンマネージ コードの例は、COM、COM +、C++ コンポーネント、ActiveX コンポーネント、および Microsoft Windows API です。</span><span class="sxs-lookup"><span data-stu-id="573dc-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="573dc-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] では、プラットフォーム呼び出しサービス、<xref:System.Runtime.InteropServices> 名前空間、C++ 相互運用性、および COM 相互運用性 (COM 相互運用機能) を通して、アンマネージ コードの相互運用を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="573dc-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="573dc-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="573dc-107">In This Section</span></span>  
 [<span data-ttu-id="573dc-108">相互運用性の概要</span><span class="sxs-lookup"><span data-stu-id="573dc-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="573dc-109">C# のマネージド コードとアンマネージド コードの間で相互運用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="573dc-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="573dc-110">方法: Visual C# の機能を使用して Office 相互運用オブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="573dc-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="573dc-111">Office のプログラミングを容易にするために Visual C# に導入されている機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="573dc-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="573dc-112">方法: COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="573dc-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="573dc-113">インデックス付きプロパティを使用して、パラメーターを持つ COM プロパティにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="573dc-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="573dc-114">方法: プラットフォーム呼び出しを使用して Wave ファイルを再生する</span><span class="sxs-lookup"><span data-stu-id="573dc-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="573dc-115">プラットフォーム呼び出しサービスを使用して、Windows オペレーティング システム上の .wav サウンド ファイルを再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="573dc-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="573dc-116">チュートリアル:Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="573dc-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="573dc-117">Excel ブックと、ブックへのリンクを含む Word 文書を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="573dc-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="573dc-118">COM クラスの例</span><span class="sxs-lookup"><span data-stu-id="573dc-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="573dc-119">C# クラスを COM オブジェクトとして公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="573dc-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="573dc-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="573dc-120">C# Language Specification</span></span>  

<span data-ttu-id="573dc-121">詳細については、「[C# 言語の仕様](../../language-reference/language-specification/index.md)」の「[基本概念](~/_csharplang/spec/unsafe-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="573dc-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="573dc-122">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="573dc-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="573dc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="573dc-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="573dc-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="573dc-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="573dc-125">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="573dc-125">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)
- [<span data-ttu-id="573dc-126">チュートリアル:Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="573dc-126">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
