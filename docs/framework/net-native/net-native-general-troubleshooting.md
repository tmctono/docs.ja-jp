---
title: .NET ネイティブの一般的なトラブルシューティング
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca0f093e85a5ac983266ba34f78021d6af6018c0
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052034"
---
# <a name="net-native-general-troubleshooting"></a><span data-ttu-id="3ac4a-102">.NET ネイティブの一般的なトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3ac4a-102">.NET Native General Troubleshooting</span></span>
<span data-ttu-id="3ac4a-103">このトピックでは、.NET ネイティブによるアプリを開発するときに発生する可能性のある潜在的な問題をトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-103">This topic describes how to troubleshoot potential issues that you might encounter when developing apps with .NET Native.</span></span>  
  
- <span data-ttu-id="3ac4a-104">**問題点:** ビルド出力ウィンドウが正しく更新されません。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-104">**Issue:** Your build output window isn't properly updated.</span></span>  
  
     <span data-ttu-id="3ac4a-105">**解決方法:** ビルド出力ウィンドウは、ビルドが完了するまで更新されません。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-105">**Resolution:** The build output window isn't updated until the build completes.</span></span> <span data-ttu-id="3ac4a-106">ビルドには数分かかる場合があるため、更新が表示されるまでに遅延が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-106">Build times may be up to several minutes, so you might experience a delay in seeing the updates.</span></span>  
  
- <span data-ttu-id="3ac4a-107">**問題点:** ARM のアプリの製品版ビルド時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-107">**Issue:** Your app’s retail build time for ARM has increased.</span></span>  
  
     <span data-ttu-id="3ac4a-108">**解決方法:** ARM デバイスにアプリを展開するときに、.NET ネイティブのインフラストラクチャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-108">**Resolution:** When you deploy an app to your ARM device, the .NET Native infrastructure is invoked.</span></span> <span data-ttu-id="3ac4a-109">このコンパイルは、リフレクションなどの非静的セマンティクスの実行が継続された状態で、多数の最適化を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-109">This compilation performs a large number of optimizations while ensuring that non-static semantics such as reflection continue to work.</span></span> <span data-ttu-id="3ac4a-110">さらに、パフォーマンスの最適化のために、.NET Framework でアプリが使用する部分は静的リンクされるため、コンパイルしてネイティブ コードにも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-110">In addition, the portion of the .NET Framework that the app uses is statically linked in for optimal performance and has to be compiled into native code as well.</span></span> <span data-ttu-id="3ac4a-111">このため、コンパイルの時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-111">This is why compilation takes longer.</span></span>  
  
     <span data-ttu-id="3ac4a-112">ただし、標準的な開発用コンピューター上で、ほとんどのアプリの標準的なコンパイルにかかる時間は 1 分以内です。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-112">However, compilation times are still within a minute of standard compilation for most apps on a standard development machine.</span></span>  <span data-ttu-id="3ac4a-113">通常、標準的な開発用コンピューターでは、.NET Framework のネイティブ イメージを生成するだけで数分かかります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-113">Typically, just generating native images for the .NET Framework on a standard development machine takes several minutes.</span></span>  <span data-ttu-id="3ac4a-114">生成されるコードを改善するための最適化をすべて行い、.NET Framework を含めても、通常、アプリのビルド時間は 1 ～ 2 分です。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-114">Even with all the optimizations to improve the generated code and with including the .NET Framework, app build times are typically a minute or two.</span></span>  
  
     <span data-ttu-id="3ac4a-115">現在も、マルチスレッド コンパイルやその他の最適化を調査して、コンパイルのパフォーマンスを改善する取り組みが続いています。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-115">We are continuing to work on improving compilation performance by investigating multi-threaded compilation and other optimizations.</span></span>  
  
- <span data-ttu-id="3ac4a-116">**問題点:**.NET ネイティブを使用して、アプリがコンパイルされたかどうかは、わかりません。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-116">**Issue:** You don’t know if your app was compiled using .NET Native.</span></span>  
  
     <span data-ttu-id="3ac4a-117">**解決方法:**.NET ネイティブ コンパイラが呼び出された場合、長いビルド時間、およびタスク マネージャーに ILC.exe や nutc_driver.exe などのさまざまな .NET ネイティブ コンポーネント プロセスを表示がわかります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-117">**Resolution:** If the .NET Native compiler is invoked, you'll notice longer build times, and Task Manager will show various .NET Native component processes such as ILC.exe and nutc_driver.exe.</span></span>  
  
     <span data-ttu-id="3ac4a-118">.NET ネイティブを使用してプロジェクトを正常にビルドした後に obj の下の出力がわかります\\*config*\ *arch*\\*projectname*. ilc\out します。最終的なネイティブ パッケージ コンテンツは、bin\\*arch*\\*config*\AppX にあります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-118">After you successfully build your project with .NET Native, you'll find the output under obj\\*config*\ *arch*\\*projectname*.ilc\out.  The final native package contents can be found under bin\\*arch*\\*config*\AppX.</span></span> <span data-ttu-id="3ac4a-119">アプリを配置した場合、最終的なネイティブ パッケージ コンテンツは \bin\\*arch*\\*config*\AppX にあります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-119">The final native package contents are under \bin\\*arch*\\*config*\AppX if you have deployed the app.</span></span>  
  
- <span data-ttu-id="3ac4a-120">**問題点:**.NET ネイティブでコンパイルされたアプリは、ランタイムの例外のスロー (通常[MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)または[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)例外) なしでコンパイルするスローされない場合。NET ネイティブです。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-120">**Issue:** Your .NET Native-compiled app is throwing runtime exceptions (typically [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) or [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exceptions) that it did not throw when compiled without .NET Native.</span></span>  
  
     <span data-ttu-id="3ac4a-121">**解決方法:**.NET ネイティブは提供されなかったため、メタデータまたは実装コードはリフレクションを介して使用できる場合は、これらの例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-121">**Resolution:** The exceptions are thrown because .NET Native did not provide either the metadata or the implementation code that is otherwise available through reflection.</span></span> <span data-ttu-id="3ac4a-122">(詳細については、「[.NET ネイティブとコンパイル](../../../docs/framework/net-native/net-native-and-compilation.md)」を参照してください)。例外を取り除くには、[ランタイム ディレクティブ (rd.xml) ファイル](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)にエントリを追加して、.NET Native ツール チェーンがメタデータまたは実装コードを実行時に使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-122">(For more information, see [.NET Native and Compilation](../../../docs/framework/net-native/net-native-and-compilation.md).) To eliminate the exception, you have to add an entry to your [runtime directives (rd.xml) file](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) so that the .NET Native tool chain can make the metadata or implementation code available at runtime.</span></span> <span data-ttu-id="3ac4a-123">次の 2 つのトラブルシューティング ツールを使用して、ランタイム ディレクティブ ファイルに追加する必要があるエントリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-123">Two troubleshooters are available that will generate the necessary entry to add to your runtime directives file:</span></span>  
  
    - <span data-ttu-id="3ac4a-124">[MissingMetadataException トラブルシューティング ツール](https://dotnet.github.io/native/troubleshooter/type.html) (型の場合)。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-124">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/type.html) for types.</span></span>  
  
    - <span data-ttu-id="3ac4a-125">[MissingMetadataException トラブルシューティング ツール](https://dotnet.github.io/native/troubleshooter/method.html) (メソッドの場合)。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-125">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/method.html) for methods.</span></span>  
  
     <span data-ttu-id="3ac4a-126">詳細については、「[リフレクションおよび .NET ネイティブ](../../../docs/framework/net-native/reflection-and-net-native.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-126">For more information, see [Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac4a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ac4a-127">See also</span></span>

- [<span data-ttu-id="3ac4a-128">Windows ストア アプリの .NET ネイティブへの移行</span><span class="sxs-lookup"><span data-stu-id="3ac4a-128">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
