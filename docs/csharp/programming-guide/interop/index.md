---
title: 相互運用性 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 3a70d2ae077552bab536e96367cab0fda1661310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75712053"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="4a3d1-102">相互運用性 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4a3d1-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="4a3d1-103">相互運用性は、アンマネージ コードへの既存の投資を保持して活用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="4a3d1-104">共通言語ランタイム (CLR) の制御下で実行されるコードは*マネージド コード*と呼ばれ、CLR の外部で実行されるコードは*アンマネージド コード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="4a3d1-105">アンマネージ コードの例は、COM、COM +、C++ コンポーネント、ActiveX コンポーネント、および Microsoft Windows API です。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="4a3d1-106">.NET Framework では、プラットフォーム呼び出しサービス、<xref:System.Runtime.InteropServices> 名前空間、C++ 相互運用性、および COM 相互運用性 (COM 相互運用機能) を通して、アンマネージ コードの相互運用を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-106">The .NET Framework enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a3d1-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4a3d1-107">In This Section</span></span>  
 [<span data-ttu-id="4a3d1-108">相互運用性の概要</span><span class="sxs-lookup"><span data-stu-id="4a3d1-108">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="4a3d1-109">C# のマネージド コードとアンマネージド コードの間で相互運用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="4a3d1-110">C# の機能を使用して Office 相互運用オブジェクトにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="4a3d1-110">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="4a3d1-111">Office のプログラミングを容易にするために Visual C# に導入されている機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="4a3d1-112">COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="4a3d1-112">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="4a3d1-113">インデックス付きプロパティを使用して、パラメーターを持つ COM プロパティにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="4a3d1-114">プラットフォーム呼び出しを使用して WAV ファイルを再生する方法</span><span class="sxs-lookup"><span data-stu-id="4a3d1-114">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="4a3d1-115">プラットフォーム呼び出しサービスを使用して、Windows オペレーティング システム上の .wav サウンド ファイルを再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="4a3d1-116">チュートリアル: Office のプログラミング</span><span class="sxs-lookup"><span data-stu-id="4a3d1-116">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="4a3d1-117">Excel ブックと、ブックへのリンクを含む Word 文書を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="4a3d1-118">COM クラスの例</span><span class="sxs-lookup"><span data-stu-id="4a3d1-118">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="4a3d1-119">C# クラスを COM オブジェクトとして公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4a3d1-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="4a3d1-120">C# Language Specification</span></span>  

<span data-ttu-id="4a3d1-121">詳細については、「[C# 言語の仕様](~/_csharplang/spec/unsafe-code.md)」の「[基本概念](/dotnet/csharp/language-reference/language-specification/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="4a3d1-122">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="4a3d1-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a3d1-123">参照</span><span class="sxs-lookup"><span data-stu-id="4a3d1-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4a3d1-124">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="4a3d1-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4a3d1-125">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="4a3d1-125">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="4a3d1-126">チュートリアル: Office のプログラミング</span><span class="sxs-lookup"><span data-stu-id="4a3d1-126">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
