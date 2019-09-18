---
title: .NET ネイティブ アプリでのランタイム例外
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27a2e0906343d115c47230c726efb74cd51d4c93
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049161"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="f7756-102">.NET ネイティブ アプリでのランタイム例外</span><span class="sxs-lookup"><span data-stu-id="f7756-102">Runtime Exceptions in .NET Native Apps</span></span>
<span data-ttu-id="f7756-103">デバッグ構成とリリース構成は完全に異なるため、ターゲット プラットフォームでユニバーサル Windows プラットフォーム アプリのリリース ビルドをテストすることは重要です。</span><span class="sxs-lookup"><span data-stu-id="f7756-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="f7756-104">既定では、デバッグ構成は .NET Core ランタイムを使用してアプリをコンパイルしますが、リリース構成は .NET ネイティブを使用してアプリをネイティブ コードにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f7756-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f7756-105">アプリのリリースバージョンをテストするときに発生する可能性のある[MissingMetadataException](missingmetadataexception-class-net-native.md)、 [MissingInteropDataException](missinginteropdataexception-class-net-native.md)、および[誤 Singruntimeartifactexception](missingruntimeartifactexception-class-net-native.md)例外の処理については、「手順 4:例外の処理については、「[.NET ネイティブの概要](getting-started-with-net-native.md)」の「手順 4: メタデータの欠落を手動で解決」、さらに「[リフレクションおよび .NET ネイティブ](reflection-and-net-native.md)」と「[ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス](runtime-directives-rd-xml-configuration-file-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7756-105">For information on dealing with the [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see "Step 4: Manually resolve missing metadata: in the [Getting Started](getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="f7756-106">デバッグ ビルドとリリース ビルド</span><span class="sxs-lookup"><span data-stu-id="f7756-106">Debug and release builds</span></span>  
 <span data-ttu-id="f7756-107">.NET Core ランタイムに対してデバッグ ビルドを実行した場合は、ネイティブ コードにコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="f7756-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="f7756-108">このため、一般にランタイムによって提供されるすべてのサービスをアプリで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f7756-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="f7756-109">一方、リリース ビルドの場合は、パフォーマンスを最大化するために、ターゲット プラットフォーム用のネイティブ コードにコンパイルされ、外部のランタイムおよびライブラリに対する依存関係のほとんどが削除され、コードが大幅に最適化されます。</span><span class="sxs-lookup"><span data-stu-id="f7756-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="f7756-110">.NET ネイティブを使用してコンパイルされたリリース ビルドをデバッグする場合:</span><span class="sxs-lookup"><span data-stu-id="f7756-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
- <span data-ttu-id="f7756-111">通常の .NET デバッグ ツールとは異なる、.NET ネイティブのデバッグ エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7756-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
- <span data-ttu-id="f7756-112">実行可能ファイルのサイズは、最大限削減されます。</span><span class="sxs-lookup"><span data-stu-id="f7756-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="f7756-113">.NET ネイティブが実行可能ファイルのサイズを削減する方法の 1 つは、ランタイムの例外メッセージを大幅にトリミングする方法です。これについては、「 [Runtime exception messages](#Messages) 」セクションでトピックとして詳細に説明しています。</span><span class="sxs-lookup"><span data-stu-id="f7756-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
- <span data-ttu-id="f7756-114">コードは大幅に最適化されます。</span><span class="sxs-lookup"><span data-stu-id="f7756-114">Your code is heavily optimized.</span></span> <span data-ttu-id="f7756-115">つまり、できる限りインライン展開が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7756-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="f7756-116">(インライン展開により、コードは外部ルーチンから呼び出し元のルーチンに移動されます。) .NET ネイティブは特殊なランタイムを備えていて、積極的なインライン展開を実装するため、デバッグするときに表示される呼び出し履歴が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="f7756-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="f7756-117">詳細については、「 [Runtime call stack](#CallStack) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7756-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7756-118">**[.NET ネイティブ ツール チェーンを使用してコンパイルする]** ボックスをオンまたはオフにすることによって、デバッグ ビルドとリリース ビルドを .NET ネイティブ ツール チェーンでコンパイルするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="f7756-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="f7756-119">ただし、Windows ストアは常に .NET ネイティブ ツールのチェーンを使用してアプリの製品バージョンをコンパイルすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7756-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>   
## <a name="runtime-exception-messages"></a><span data-ttu-id="f7756-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="f7756-120">Runtime exception messages</span></span>  
 <span data-ttu-id="f7756-121">アプリケーションの実行可能ファイルのサイズを最小限に抑えるために、.NET ネイティブは例外メッセージの全文を組み込みません。</span><span class="sxs-lookup"><span data-stu-id="f7756-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="f7756-122">そのため、リリース ビルドでスローされるランタイム例外では、例外メッセージの全文が表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7756-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="f7756-123">代わりに、部分的な文字列を含むテキストが、詳細を示すリンクと共に表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7756-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="f7756-124">たとえば、以下のような例外情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7756-124">For example, the exception information may appear as:</span></span>  
  
```output
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="f7756-125">完全な例外メッセージが必要な場合は、代わりにデバッグ ビルドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7756-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="f7756-126">たとえば、リリース ビルドからの上記の例外情報は、デバッグ ビルドでは以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7756-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```output
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>   
## <a name="runtime-call-stack"></a><span data-ttu-id="f7756-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="f7756-127">Runtime call stack</span></span>  
 <span data-ttu-id="f7756-128">インライン展開および他の最適化のために、.NET ネイティブ ツール チェーンでコンパイルされたアプリで表示される呼び出し履歴では、ランタイム例外へのパスを明確に識別できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7756-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="f7756-129">完全なスタックを取得するには、代わりにデバッグ ビルドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7756-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7756-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7756-130">See also</span></span>

- [<span data-ttu-id="f7756-131">Windows ユニバーサルアプリのデバッグ .NET ネイティブ</span><span class="sxs-lookup"><span data-stu-id="f7756-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="f7756-132">はじめに</span><span class="sxs-lookup"><span data-stu-id="f7756-132">Getting Started</span></span>](getting-started-with-net-native.md)
