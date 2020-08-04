---
title: 相互運用性 - C# プログラミング ガイド
description: 相互運用性では、共通言語ランタイムで実行されるコードのほかに、アンマネージド コードをサポートしています。 これらのリソースを使用して、相互運用のオプションを理解してください。
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: d85eb51107d50e023270fcbe1ef6e08a7788ae78
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302972"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="a8b16-104">相互運用性 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a8b16-104">Interoperability (C# Programming Guide)</span></span>

<span data-ttu-id="a8b16-105">相互運用性は、アンマネージ コードへの既存の投資を保持して活用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a8b16-105">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="a8b16-106">共通言語ランタイム (CLR) の制御下で実行されるコードは*マネージド コード*と呼ばれ、CLR の外部で実行されるコードは*アンマネージド コード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a8b16-106">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="a8b16-107">アンマネージ コードの例は、COM、COM +、C++ コンポーネント、ActiveX コンポーネント、および Microsoft Windows API です。</span><span class="sxs-lookup"><span data-stu-id="a8b16-107">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
<span data-ttu-id="a8b16-108">.NET では、プラットフォーム呼び出しサービス、<xref:System.Runtime.InteropServices> 名前空間、C++ 相互運用性、および COM 相互運用性 (COM 相互運用機能) を通して、アンマネージド コードの相互運用を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="a8b16-108">.NET enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8b16-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a8b16-109">In This Section</span></span>  
 [<span data-ttu-id="a8b16-110">相互運用性の概要</span><span class="sxs-lookup"><span data-stu-id="a8b16-110">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="a8b16-111">C# のマネージド コードとアンマネージド コードの間で相互運用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8b16-111">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="a8b16-112">C# の機能を使用して Office 相互運用オブジェクトにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="a8b16-112">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="a8b16-113">Office のプログラミングを容易にするために Visual C# に導入されている機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8b16-113">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="a8b16-114">COM 相互運用機能を使用したプログラミングでインデックス付きプロパティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="a8b16-114">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="a8b16-115">インデックス付きプロパティを使用して、パラメーターを持つ COM プロパティにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8b16-115">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="a8b16-116">プラットフォーム呼び出しを使用して WAV ファイルを再生する方法</span><span class="sxs-lookup"><span data-stu-id="a8b16-116">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="a8b16-117">プラットフォーム呼び出しサービスを使用して、Windows オペレーティング システム上の .wav サウンド ファイルを再生する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8b16-117">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="a8b16-118">チュートリアル:Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="a8b16-118">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="a8b16-119">Excel ブックと、ブックへのリンクを含む Word 文書を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8b16-119">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="a8b16-120">COM クラスの例</span><span class="sxs-lookup"><span data-stu-id="a8b16-120">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="a8b16-121">C# クラスを COM オブジェクトとして公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8b16-121">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a8b16-122">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a8b16-122">C# Language Specification</span></span>  

<span data-ttu-id="a8b16-123">詳細については、「[C# 言語の仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の「[基本概念](~/_csharplang/spec/unsafe-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8b16-123">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a8b16-124">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="a8b16-124">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a8b16-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8b16-125">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a8b16-126">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a8b16-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a8b16-127">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="a8b16-127">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="a8b16-128">チュートリアル: Office プログラミング</span><span class="sxs-lookup"><span data-stu-id="a8b16-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
