---
title: .NET ネイティブの一般的なトラブルシューティング
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5f61b0e250c4f51a966bc60959f7559d8e2fe2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049397"
---
# <a name="net-native-general-troubleshooting"></a><span data-ttu-id="c1ec2-102">.NET ネイティブの一般的なトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c1ec2-102">.NET Native General Troubleshooting</span></span>

<span data-ttu-id="c1ec2-103">このトピックでは、.NET ネイティブでアプリを開発するときに発生する可能性がある問題のトラブルシューティング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-103">This topic describes how to troubleshoot potential issues that you might encounter when developing apps with .NET Native.</span></span>

- <span data-ttu-id="c1ec2-104">**問題点:** ビルド出力ウィンドウが正しく更新されていません。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-104">**Issue:** Your build output window isn't properly updated.</span></span>

  <span data-ttu-id="c1ec2-105">**解決方法:** ビルドの出力ウィンドウは、ビルドが完了するまで更新されません。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-105">**Resolution:** The build output window isn't updated until the build completes.</span></span> <span data-ttu-id="c1ec2-106">ビルドには数分かかる場合があるため、更新が表示されるまでに遅延が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-106">Build times may be up to several minutes, so you might experience a delay in seeing the updates.</span></span>

- <span data-ttu-id="c1ec2-107">**問題点:** ARM のアプリの製品ビルド時間が長くなっています。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-107">**Issue:** Your app’s retail build time for ARM has increased.</span></span>

  <span data-ttu-id="c1ec2-108">**解決方法:** ARM デバイスにアプリをデプロイすると、.NET ネイティブインフラストラクチャが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-108">**Resolution:** When you deploy an app to your ARM device, the .NET Native infrastructure is invoked.</span></span> <span data-ttu-id="c1ec2-109">このコンパイルは、リフレクションなどの非静的セマンティクスの実行が継続された状態で、多数の最適化を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-109">This compilation performs a large number of optimizations while ensuring that non-static semantics such as reflection continue to work.</span></span> <span data-ttu-id="c1ec2-110">さらに、パフォーマンスの最適化のために、.NET Framework でアプリが使用する部分は静的リンクされるため、コンパイルしてネイティブ コードにも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-110">In addition, the portion of the .NET Framework that the app uses is statically linked in for optimal performance and has to be compiled into native code as well.</span></span> <span data-ttu-id="c1ec2-111">このため、コンパイルの時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-111">This is why compilation takes longer.</span></span>

  <span data-ttu-id="c1ec2-112">ただし、標準的な開発用コンピューター上で、ほとんどのアプリの標準的なコンパイルにかかる時間は 1 分以内です。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-112">However, compilation times are still within a minute of standard compilation for most apps on a standard development machine.</span></span>  <span data-ttu-id="c1ec2-113">通常、標準的な開発用コンピューターでは、.NET Framework のネイティブ イメージを生成するだけで数分かかります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-113">Typically, just generating native images for the .NET Framework on a standard development machine takes several minutes.</span></span>  <span data-ttu-id="c1ec2-114">生成されるコードを改善するための最適化をすべて行い、.NET Framework を含めても、通常、アプリのビルド時間は 1 ～ 2 分です。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-114">Even with all the optimizations to improve the generated code and with including the .NET Framework, app build times are typically a minute or two.</span></span>

  <span data-ttu-id="c1ec2-115">現在も、マルチスレッド コンパイルやその他の最適化を調査して、コンパイルのパフォーマンスを改善する取り組みが続いています。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-115">We are continuing to work on improving compilation performance by investigating multi-threaded compilation and other optimizations.</span></span>

- <span data-ttu-id="c1ec2-116">**問題点:** アプリが .NET ネイティブを使用してコンパイルされたかどうかはわかりません。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-116">**Issue:** You don’t know if your app was compiled using .NET Native.</span></span>

  <span data-ttu-id="c1ec2-117">**解決方法:** .NET ネイティブコンパイラが呼び出されると、ビルド時間が長くなり、タスクマネージャーによって、ILC や nutc_driver などのさまざまな .NET ネイティブコンポーネントプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-117">**Resolution:** If the .NET Native compiler is invoked, you'll notice longer build times, and Task Manager will show various .NET Native component processes such as ILC.exe and nutc_driver.exe.</span></span>

  <span data-ttu-id="c1ec2-118">.NET ネイティブでプロジェクトを正常にビルドすると、obj\\*config*\ *arch*\\*projectname*. ilc\out の下に出力が表示されます。最終的なネイティブ パッケージ コンテンツは、bin\\*arch*\\*config*\AppX にあります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-118">After you successfully build your project with .NET Native, you'll find the output under obj\\*config*\ *arch*\\*projectname*.ilc\out.  The final native package contents can be found under bin\\*arch*\\*config*\AppX.</span></span> <span data-ttu-id="c1ec2-119">アプリを配置した場合、最終的なネイティブ パッケージ コンテンツは \bin\\*arch*\\*config*\AppX にあります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-119">The final native package contents are under \bin\\*arch*\\*config*\AppX if you have deployed the app.</span></span>

- <span data-ttu-id="c1ec2-120">**問題点:** .NET ネイティブコンパイルされたアプリは、.NET ネイティブせずにコンパイルしたときにスローされないランタイム例外 (通常は[MissingMetadataException](missingmetadataexception-class-net-native.md)または[誤 Singruntimeartifactexception](missingruntimeartifactexception-class-net-native.md)例外) をスローしています。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-120">**Issue:** Your .NET Native-compiled app is throwing runtime exceptions (typically [MissingMetadataException](missingmetadataexception-class-net-native.md) or [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions) that it did not throw when compiled without .NET Native.</span></span>

  <span data-ttu-id="c1ec2-121">**解決方法:** 例外がスローされるのは、リフレクションを通じて使用可能なメタデータまたは実装コードを .NET ネイティブが提供しなかったためです。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-121">**Resolution:** The exceptions are thrown because .NET Native did not provide either the metadata or the implementation code that is otherwise available through reflection.</span></span> <span data-ttu-id="c1ec2-122">(詳細については、「[.NET ネイティブとコンパイル](net-native-and-compilation.md)」を参照してください)。例外を取り除くには、[ランタイム ディレクティブ (rd.xml) ファイル](runtime-directives-rd-xml-configuration-file-reference.md)にエントリを追加して、.NET Native ツール チェーンがメタデータまたは実装コードを実行時に使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-122">(For more information, see [.NET Native and Compilation](net-native-and-compilation.md).) To eliminate the exception, you have to add an entry to your [runtime directives (rd.xml) file](runtime-directives-rd-xml-configuration-file-reference.md) so that the .NET Native tool chain can make the metadata or implementation code available at runtime.</span></span> <span data-ttu-id="c1ec2-123">次の 2 つのトラブルシューティング ツールを使用して、ランタイム ディレクティブ ファイルに追加する必要があるエントリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-123">Two troubleshooters are available that will generate the necessary entry to add to your runtime directives file:</span></span>

  - <span data-ttu-id="c1ec2-124">[MissingMetadataException トラブルシューティング ツール](https://dotnet.github.io/native/troubleshooter/type.html) (型の場合)。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-124">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/type.html) for types.</span></span>

  - <span data-ttu-id="c1ec2-125">[MissingMetadataException トラブルシューティング ツール](https://dotnet.github.io/native/troubleshooter/method.html) (メソッドの場合)。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-125">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/method.html) for methods.</span></span>

  <span data-ttu-id="c1ec2-126">詳細については、「[リフレクションおよび .NET ネイティブ](reflection-and-net-native.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1ec2-126">For more information, see [Reflection and .NET Native](reflection-and-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1ec2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1ec2-127">See also</span></span>

- [<span data-ttu-id="c1ec2-128">Windows ストア アプリの .NET ネイティブへの移行</span><span class="sxs-lookup"><span data-stu-id="c1ec2-128">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)
