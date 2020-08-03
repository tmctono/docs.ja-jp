---
title: .NET Framework で互換性のために残されている機能
description: .NET クラス ライブラリでメンバーを旧版のものとしてマークする方法を確認します。 ObsoleteAttribute 属性、旧版の型とメンバーを処理する方法などについて理解します。
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
ms.openlocfilehash: 2f39f5ec614b669f3a0f63677cb6f8a6f9ed11cf
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925801"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="cf42c-104">クラス ライブラリ内にある旧版のもの</span><span class="sxs-lookup"><span data-stu-id="cf42c-104">What's obsolete in the .NET Framework class library</span></span>

<span data-ttu-id="cf42c-105">.NET の変化の推移。</span><span class="sxs-lookup"><span data-stu-id="cf42c-105">.NET changes over time.</span></span> <span data-ttu-id="cf42c-106">バージョンが新しくなるたびに、新しい機能を提供する新しい型と新しいメンバーが追加されています。</span><span class="sxs-lookup"><span data-stu-id="cf42c-106">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="cf42c-107">既存の型とそのメンバーも変更されています。</span><span class="sxs-lookup"><span data-stu-id="cf42c-107">Existing types and their members also change over time.</span></span> <span data-ttu-id="cf42c-108">たとえば、一部の型は、その型がサポートするテクノロジが新しいテクノロジに置き換えられることで重要度が下がり、一部のメソッドは、何らかの形で優れた新しいメソッドに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="cf42c-108">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are superior in some way.</span></span>

<span data-ttu-id="cf42c-109">.NET Framework と共通言語ランタイムでは、下位互換性をサポートするように努めています (.NET Framework の特定のバージョンで開発したアプリケーションを、.NET Framework の次期バージョンで実行できるようにするためです)。</span><span class="sxs-lookup"><span data-stu-id="cf42c-109">.NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of .NET Framework to run on the next version of .NET Framework).</span></span> <span data-ttu-id="cf42c-110">そのため、型または型のメンバーを単純に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf42c-110">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="cf42c-111">そこで、.NET では、型または型のメンバーが使用されなくなったことを示すために、その型またはメンバーを旧式 (互換性のために残されている) または非推奨として指定しています。</span><span class="sxs-lookup"><span data-stu-id="cf42c-111">Instead, .NET indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="cf42c-112">型またはメンバーを非推奨とする場合は、開発者がその型またはメンバーが削除予定であることを認識してその削除に対応できるように、指定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf42c-112">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="cf42c-113">ただし、そのような型またはメンバーを使用する既存のコードは、.NET の次期バージョンで引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-113">However, existing code that uses the type or member continues to run in the new version of .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="cf42c-114">"*旧式 (互換性のために残されている)* " という用語と "*非推奨*" という用語は、.NET の型とメンバーに対して使用する場合は同じ意味です。</span><span class="sxs-lookup"><span data-stu-id="cf42c-114">The terms *obsolete* and *deprecated* have the same meaning when applied to .NET types and members.</span></span>

## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="cf42c-115">ObsoleteAttribute 属性</span><span class="sxs-lookup"><span data-stu-id="cf42c-115">The ObsoleteAttribute attribute</span></span>

<span data-ttu-id="cf42c-116">.NET Framework では、型または型のメンバーが旧式であることを示すために、その型またはメンバーに <xref:System.ObsoleteAttribute> 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-116">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="cf42c-117">この属性が型またはメンバーに適用されている場合、その型またはメンバーは .NET Framework の将来のバージョンで削除される予定であることを意味します。ただし、そのメンバーを使用するコンパイル済みコードに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="cf42c-117">Applying the attribute to a type or member indicates that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>

<span data-ttu-id="cf42c-118">型または型のメンバーが旧式であることを示す以外に、<xref:System.ObsoleteAttribute> は、その型またはメンバーが含まれているソース コードをコンパイラで処理する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-118">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="cf42c-119">コードをコンパイルするが警告メッセージを出力するようにすることも、旧式の型またはメンバーの使用をエラーとして扱うこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-119">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="cf42c-120">前者の場合、コードを正常にコンパイルできますが、警告メッセージによって型またはメンバーが旧式であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-120">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="cf42c-121">後者の場合、コンパイルは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-121">In the second case, compilation fails.</span></span>

<span data-ttu-id="cf42c-122">コンパイルで警告メッセージではなくエラーが生成される場合でも、<xref:System.ObsoleteAttribute> は実行時の動作には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="cf42c-122">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="cf42c-123">つまり、旧式の型またはメンバーを使用しているが正常にコンパイルされたアプリケーションは、常に正常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-123">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="cf42c-124">旧式の型またはメンバーを使用するアプリケーションを再コンパイルしようとした場合にのみ失敗します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-124">Only the attempt to recompile an application that uses the type or member fails.</span></span>

## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="cf42c-125">旧式の型とメンバーを処理する方法</span><span class="sxs-lookup"><span data-stu-id="cf42c-125">How to handle obsolete types and members</span></span>

<span data-ttu-id="cf42c-126">既存のコードをアップグレードし、再コンパイルする場合に、コンパイラの警告を生成する旧式の型またはメンバーをアプリケーションで使用しても、まったく問題ありません。</span><span class="sxs-lookup"><span data-stu-id="cf42c-126">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="cf42c-127">ただし、コンパイラの警告メッセージを確認して、アプリケーション コードを変更する必要があるかどうか判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf42c-127">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="cf42c-128">代わりとなる適切な方法がメッセージに示されていない場合は、次のいずれかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf42c-128">If the message does not point to a suitable alternative, you should do either of the following:</span></span>

- <span data-ttu-id="cf42c-129">可能であれば、コードを変更して旧式の型またはメンバーの使用を止めます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-129">Change your code by removing the use of the type or member, if possible.</span></span>

     <span data-ttu-id="cf42c-130">\- または -</span><span class="sxs-lookup"><span data-stu-id="cf42c-130">-or-</span></span>

- <span data-ttu-id="cf42c-131">このテクノロジ分野に関するドキュメントを確認して、非推奨の機能の使用に対する対応方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-131">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>

<span data-ttu-id="cf42c-132">既存のコードは、.NET Framework の新しいバージョンに対して再コンパイルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf42c-132">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="cf42c-133">代わりに、既存のコンパイル済みコードの実行対象である .NET Framework のバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-133">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="cf42c-134">たとえば、.NET Framework 3.5 に対してコンパイルされた app1.exe というアプリケーションがあるものの、このアプリケーションを .NET Framework 4.5 に対して実行する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="cf42c-134">For example, suppose that you have an application named app1.exe that was compiled against the .NET Framework 3.5, but you want the application to run against the .NET Framework 4.5.</span></span> <span data-ttu-id="cf42c-135">この場合、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="cf42c-135">This requires the following steps:</span></span>

1. <span data-ttu-id="cf42c-136">メイン実行可能ファイルの構成ファイルを作成し、その名前を *appName*.exe.config にします。*appName* は、アプリケーションの実行可能ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="cf42c-136">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="cf42c-137">このトピックの例の *app1.exe* というアプリケーションの場合は、*app1.exe.config* という名前の構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-137">For the application named *app1.exe* in our example, you would create a configuration file named *app1.exe.config*.</span></span>

2. <span data-ttu-id="cf42c-138">次のコードを構成ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="cf42c-138">Add the following to the configuration file.</span></span>

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

<span data-ttu-id="cf42c-139">.NET Framework の特定のバージョンを対象とするには、次の文字列値のいずれかを `version` 属性に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cf42c-139">To target a specific version of .NET Framework, assign one of the following string values to the `version` attribute:</span></span>

|<span data-ttu-id="cf42c-140">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="cf42c-140">.NET Framework version</span></span>|<span data-ttu-id="cf42c-141">`version` 文字列</span><span class="sxs-lookup"><span data-stu-id="cf42c-141">`version` string</span></span>|
|-|-|
|<span data-ttu-id="cf42c-142">4.8</span><span class="sxs-lookup"><span data-stu-id="cf42c-142">4.8</span></span>|<span data-ttu-id="cf42c-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="cf42c-143">v4.0</span></span>|
|<span data-ttu-id="cf42c-144">4.7 (4.7.1 と 4.7.2 を含む)</span><span class="sxs-lookup"><span data-stu-id="cf42c-144">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="cf42c-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="cf42c-145">v4.0</span></span>|
|<span data-ttu-id="cf42c-146">4.6 (4.6.1 と 4.6.2 を含む)</span><span class="sxs-lookup"><span data-stu-id="cf42c-146">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="cf42c-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="cf42c-147">v4.0</span></span>|
|<span data-ttu-id="cf42c-148">4.5 (4.5.1 および 4.5.2 を含む)</span><span class="sxs-lookup"><span data-stu-id="cf42c-148">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="cf42c-149">v4.0</span><span class="sxs-lookup"><span data-stu-id="cf42c-149">v4.0</span></span>|
|<span data-ttu-id="cf42c-150">4</span><span class="sxs-lookup"><span data-stu-id="cf42c-150">4</span></span>|<span data-ttu-id="cf42c-151">v4.0</span><span class="sxs-lookup"><span data-stu-id="cf42c-151">v4.0</span></span>|
|<span data-ttu-id="cf42c-152">3.5</span><span class="sxs-lookup"><span data-stu-id="cf42c-152">3.5</span></span>|<span data-ttu-id="cf42c-153">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="cf42c-153">v2.0.50727</span></span>|
|<span data-ttu-id="cf42c-154">2.0</span><span class="sxs-lookup"><span data-stu-id="cf42c-154">2.0</span></span>|<span data-ttu-id="cf42c-155">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="cf42c-155">v2.0.50727</span></span>|
|<span data-ttu-id="cf42c-156">1.1</span><span class="sxs-lookup"><span data-stu-id="cf42c-156">1.1</span></span>|<span data-ttu-id="cf42c-157">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="cf42c-157">v1.1.4322</span></span>|
|<span data-ttu-id="cf42c-158">1</span><span class="sxs-lookup"><span data-stu-id="cf42c-158">1.0</span></span>|<span data-ttu-id="cf42c-159">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="cf42c-159">v1.0.3705</span></span>|

## <a name="obsolete-apis-for-net-framework-45-and-later-versions"></a><span data-ttu-id="cf42c-160">.NET Framework 4.5 以降のバージョンの互換性のために残されている API</span><span class="sxs-lookup"><span data-stu-id="cf42c-160">Obsolete APIs for .NET Framework 4.5 and later versions</span></span>

- [<span data-ttu-id="cf42c-161">旧版の .NET Framework の型</span><span class="sxs-lookup"><span data-stu-id="cf42c-161">Obsolete Types</span></span>](obsolete-types.md)
- [<span data-ttu-id="cf42c-162">互換性のために残されているメンバー</span><span class="sxs-lookup"><span data-stu-id="cf42c-162">Obsolete Members</span></span>](obsolete-members.md)

## <a name="obsolete-apis-for-previous-versions"></a><span data-ttu-id="cf42c-163">以前のバージョンの互換性のために残されている API</span><span class="sxs-lookup"><span data-stu-id="cf42c-163">Obsolete APIs for previous versions</span></span>

- <span data-ttu-id="cf42c-164">[.NET Framework 4 で互換性のために残されている型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf42c-164">[Obsolete Types in .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span></span>
- <span data-ttu-id="cf42c-165">[.NET Framework 4 で互換性のために残されているメンバー](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cf42c-165">[Obsolete Members in .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span></span>
- <span data-ttu-id="cf42c-166">[.NET Framework 3.5 Obsolete List (.NET Framework 3.5 の互換性のために残されている機能の一覧)](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="cf42c-166">[.NET Framework 3.5 Obsolete List](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span></span>
- <span data-ttu-id="cf42c-167">[.NET Framework 2.0 Obsolete List (.NET Framework 2.0 の互換性のために残されている機能の一覧)](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="cf42c-167">[.NET Framework 2.0 Obsolete List](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="cf42c-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf42c-168">See also</span></span>

- [<span data-ttu-id="cf42c-169">\<supportedRuntime> 要素</span><span class="sxs-lookup"><span data-stu-id="cf42c-169">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
