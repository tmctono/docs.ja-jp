---
title: NET の安全なコーディング ガイドライン
description: で使用するコードを設計します。NET によって適用されるアクセス許可およびその他の強制により、悪意のあるコードがデータにアクセスしたり、他のアクションを実行したりすることを防止できます。
ms.date: 06/28/2018
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET], security
- code security, options
- security-neutral code
- security [.NET], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
ms.openlocfilehash: 05f7e039ecdc0cd33baa015872924fb9e1f078aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187725"
---
# <a name="secure-coding-guidelines"></a><span data-ttu-id="52b52-103">安全なコーディングガイドライン</span><span class="sxs-lookup"><span data-stu-id="52b52-103">Secure coding guidelines</span></span>

<span data-ttu-id="52b52-104">エビデンスベース セキュリティとコード アクセス セキュリティは、セキュリティを実現するための強力で明示的なメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="52b52-104">Evidence-based security and code access security provide very powerful, explicit mechanisms to implement security.</span></span> <span data-ttu-id="52b52-105">ほとんどのアプリケーション コードは、.NET によって実装されたインフラストラクチャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52b52-105">Most application code can simply use the infrastructure implemented by .NET.</span></span> <span data-ttu-id="52b52-106">場合によっては、アプリケーション特有の追加のセキュリティが必要になります。これは、セキュリティ システムを拡張するか、または新しい特有の方法を使用して構築されます。</span><span class="sxs-lookup"><span data-stu-id="52b52-106">In some cases, additional application-specific security is required, built either by extending the security system or by using new ad hoc methods.</span></span>

<span data-ttu-id="52b52-107">NET が適用するアクセス許可やその他のコードの適用を使用して、悪意のあるコードが、悪意のあるコードから、不要な情報にアクセスしたり、その他の望ましくないアクションを実行したりすることを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-107">Using .NET enforced permissions and other enforcement in your code, you should erect barriers to prevent malicious code from accessing information that you don't want it to have or performing other undesirable actions.</span></span> <span data-ttu-id="52b52-108">また、信頼されるコードを使用するすべての想定されるシナリオで、セキュリティと使いやすさのバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-108">Additionally, you must strike a balance between security and usability in all the expected scenarios using trusted code.</span></span>

<span data-ttu-id="52b52-109">この概要では、セキュリティ システムと連携するようコードを設計するさまざまな方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="52b52-109">This overview describes the different ways code can be designed to work with the security system.</span></span>

## <a name="securing-resource-access"></a><span data-ttu-id="52b52-110">リソース アクセスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="52b52-110">Securing resource access</span></span>

<span data-ttu-id="52b52-111">コードを設計して作成する場合、作成元が不明なコードを使用したり呼び出したりする際は特に、コードがリソースに対して持つアクセス権の保護と制限を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-111">When designing and writing your code, you need to protect and limit the access that code has to resources, especially when using or invoking code of unknown origin.</span></span> <span data-ttu-id="52b52-112">そのため、コードの安全性を確保するために次の点に注意します。</span><span class="sxs-lookup"><span data-stu-id="52b52-112">So, keep in mind the following techniques to ensure your code is secure:</span></span>

- <span data-ttu-id="52b52-113">コード アクセス セキュリティ (CAS) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-113">Do not use Code Access Security (CAS).</span></span>

- <span data-ttu-id="52b52-114">部分的に信頼されたコードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-114">Do not use partial trusted code.</span></span>

- <span data-ttu-id="52b52-115">[部分的に信頼された呼び出し元を許可](xref:System.Security.AllowPartiallyTrustedCallersAttribute)する属性 (APTCA) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-115">Do not use the [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) attribute (APTCA).</span></span>

- <span data-ttu-id="52b52-116">.NET リモート処理を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-116">Do not use .NET Remoting.</span></span>

- <span data-ttu-id="52b52-117">分散コンポーネント オブジェクト モデル (DCOM) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-117">Do not use Distributed Component Object Model (DCOM).</span></span>

- <span data-ttu-id="52b52-118">バイナリ フォーマッタを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-118">Do not use binary formatters.</span></span>

<span data-ttu-id="52b52-119">コード アクセス セキュリティおよび透過的なコードは、部分的に信頼されたコードのセキュリティ境界としてサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="52b52-119">Code Access Security and Security-Transparent Code are not supported as a security boundary with partially trusted code.</span></span> <span data-ttu-id="52b52-120">発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="52b52-120">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="52b52-121">代わりのセキュリティ対策は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="52b52-121">The alternative security measures are:</span></span>

- <span data-ttu-id="52b52-122">仮想化</span><span class="sxs-lookup"><span data-stu-id="52b52-122">Virtualization</span></span>

- <span data-ttu-id="52b52-123">AppContainers</span><span class="sxs-lookup"><span data-stu-id="52b52-123">AppContainers</span></span>

- <span data-ttu-id="52b52-124">オペレーティング システム (OS) のユーザーおよびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52b52-124">Operating system (OS) users and permissions</span></span>

- <span data-ttu-id="52b52-125">Hyper-V コンテナー</span><span class="sxs-lookup"><span data-stu-id="52b52-125">Hyper-V containers</span></span>

## <a name="security-neutral-code"></a><span data-ttu-id="52b52-126">セキュリティに依存しないコード</span><span class="sxs-lookup"><span data-stu-id="52b52-126">Security-neutral code</span></span>

<span data-ttu-id="52b52-127">セキュリティ中立なコードは、セキュリティ システムに対して明示的な操作を何も行いません。</span><span class="sxs-lookup"><span data-stu-id="52b52-127">Security-neutral code does nothing explicit with the security system.</span></span> <span data-ttu-id="52b52-128">これは何であれ自分が受け取ったアクセス許可を使用して動作します。</span><span class="sxs-lookup"><span data-stu-id="52b52-128">It runs with whatever permissions it receives.</span></span> <span data-ttu-id="52b52-129">保護された操作に関連付けられたセキュリティ例外 (ファイルやネットワークの使用など) をキャッチできないアプリケーションでは、処理されない例外が発生する可能性がありますが、セキュリティに依存しないコードは依然として .NET のセキュリティ テクノロジを利用します。.</span><span class="sxs-lookup"><span data-stu-id="52b52-129">Although applications that fail to catch security exceptions associated with protected operations (such as using files, networking, and so on) can result in an unhandled exception, security-neutral code still takes advantage of the security technologies in .NET.</span></span>

<span data-ttu-id="52b52-130">セキュリティ中立なライブラリは、理解しておくべき特別な特性を持っています。</span><span class="sxs-lookup"><span data-stu-id="52b52-130">A security-neutral library has special characteristics that you should understand.</span></span> <span data-ttu-id="52b52-131">ライブラリに、ファイルを使用する API 要素、またはアンマネージ コードを呼び出す API 要素が用意されている場合を考えます。</span><span class="sxs-lookup"><span data-stu-id="52b52-131">Suppose your library provides API elements that use files or call unmanaged code.</span></span> <span data-ttu-id="52b52-132">コードに対応するアクセス許可がない場合は、説明どおりに実行されません。</span><span class="sxs-lookup"><span data-stu-id="52b52-132">If your code doesn't have the corresponding permission, it won't run as described.</span></span> <span data-ttu-id="52b52-133">しかし、コードがアクセス許可を持っているとしても、そのコードを呼び出すアプリケーション コードが同じアクセス許可を持っていなければ、正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="52b52-133">However, even if the code has the permission, any application code that calls it must have the same permission in order to work.</span></span> <span data-ttu-id="52b52-134">呼び出し元のコードに適切なアクセス許可がない<xref:System.Security.SecurityException>場合は、コード アクセス セキュリティ スタック ウォークの結果として a が表示されます。</span><span class="sxs-lookup"><span data-stu-id="52b52-134">If the calling code doesn't have the right permission, a <xref:System.Security.SecurityException> appears as a result of the code access security stack walk.</span></span>

## <a name="application-code-that-isnt-a-reusable-component"></a><span data-ttu-id="52b52-135">再利用可能なコンポーネントではないアプリケーション コード</span><span class="sxs-lookup"><span data-stu-id="52b52-135">Application code that isn't a reusable component</span></span>

<span data-ttu-id="52b52-136">コードが他のコードから呼び出されないアプリケーションの一部である場合、セキュリティは単純であり、特別なコーディングは必要ない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-136">If your code is part of an application that won't be called by other code, security is simple and special coding might not be required.</span></span> <span data-ttu-id="52b52-137">ただし、悪意のあるコードがそのコードを呼び出す可能性があることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="52b52-137">However, remember that malicious code can call your code.</span></span> <span data-ttu-id="52b52-138">悪意のあるコードによるリソースへのアクセスをコード アクセス セキュリティが阻止する可能性もありますが、機密情報を含んだフィールドやプロパティの値をそのようなコードが読み取ることも考えられます。</span><span class="sxs-lookup"><span data-stu-id="52b52-138">While code access security might stop malicious code from accessing resources, such code could still read values of your fields or properties that might contain sensitive information.</span></span>

<span data-ttu-id="52b52-139">また、コードがインターネットやその他の信頼できないソースからのユーザー入力を受け付ける場合には、悪意のある入力にも注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-139">Additionally, if your code accepts user input from the Internet or other unreliable sources, you must be careful about malicious input.</span></span>

## <a name="managed-wrapper-to-native-code-implementation"></a><span data-ttu-id="52b52-140">ネイティブ コード実装へのマネージ ラッパー</span><span class="sxs-lookup"><span data-stu-id="52b52-140">Managed wrapper to native code implementation</span></span>

<span data-ttu-id="52b52-141">一般にこのシナリオは、何らかの有用な機能がネイティブ コードで実装されており、これをマネージド コードで利用したいというケースに該当します。</span><span class="sxs-lookup"><span data-stu-id="52b52-141">Typically in this scenario, some useful functionality is implemented in native code that you want to make available to managed code.</span></span> <span data-ttu-id="52b52-142">マネージド ラッパーは、プラットフォーム呼び出しか COM 相互運用を使用して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="52b52-142">Managed wrappers are easy to write using either platform invoke or COM interop.</span></span> <span data-ttu-id="52b52-143">ただしこの場合には、操作を成功させるために、ラッパーの呼び出し元がアンマネージ コードの権利を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-143">However, if you do this, callers of your wrappers must have unmanaged code rights in order to succeed.</span></span> <span data-ttu-id="52b52-144">既定のポリシーでは、イントラネットまたはインターネットからダウンロードされたコードがラッパーで動作しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="52b52-144">Under default policy, this means that code downloaded from an intranet or the Internet won't work with the wrappers.</span></span>

<span data-ttu-id="52b52-145">これらのラッパーを使用するすべてのアプリケーションにアンマネージ コードの権限を与える代わりに、ラッパー コードにのみこれらの権限を与える方がよいです。</span><span class="sxs-lookup"><span data-stu-id="52b52-145">Instead of giving unmanaged code rights to all applications that use these wrappers, it's better to give these rights only to the wrapper code.</span></span> <span data-ttu-id="52b52-146">基になる機能が何もリソースを公開しておらず、かつ実装も同様に安全である場合、ラッパーは、自分の権利をアサートしさえすれば、あらゆるコードが自分を通して呼び出しを行えるようにできます。</span><span class="sxs-lookup"><span data-stu-id="52b52-146">If the underlying functionality exposes no resources and the implementation is likewise safe, the wrapper only needs to assert its rights, which enables any code to call through it.</span></span> <span data-ttu-id="52b52-147">リソースが関係する場合のセキュリティ コーディングは、次のセクションで説明するライブラリ コードのケースと同じです。</span><span class="sxs-lookup"><span data-stu-id="52b52-147">When resources are involved, security coding should be the same as the library code case described in the next section.</span></span> <span data-ttu-id="52b52-148">ラッパーはこれらのリソースに対して呼び出し元を公開する可能性があるため、ネイティブ コードの安全性を慎重に確認する必要があり、その責任はラッパーにあります。</span><span class="sxs-lookup"><span data-stu-id="52b52-148">Because the wrapper is potentially exposing callers to these resources, careful verification of the safety of the native code is necessary and is the wrapper's responsibility.</span></span>

## <a name="library-code-that-exposes-protected-resources"></a><span data-ttu-id="52b52-149">保護されたリソースを公開するライブラリ コード</span><span class="sxs-lookup"><span data-stu-id="52b52-149">Library code that exposes protected resources</span></span>

<span data-ttu-id="52b52-150">次のアプローチは、セキュリティ コーディングに対して最も強力で危険な (誤った場合) です: ライブラリは、.NET クラスが強制するように、他のコードが他のコードからアクセスできない特定のリソースにアクセスするためのインターフェイスとして機能します。使用するリソースのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="52b52-150">The following approach is the most powerful and hence potentially dangerous (if done incorrectly) for security coding: your library serves as an interface for other code to access certain resources that aren't otherwise available, just as the .NET classes enforce permissions for the resources they use.</span></span> <span data-ttu-id="52b52-151">どこでリソースを公開しようと、コードはまずそのリソースに適したアクセス許可を要求し (つまりセキュリティ チェックを実行しなければなりません)、それから通常は実際の操作を実行するための権利をアサートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b52-151">Wherever you expose a resource, your code must first demand the permission appropriate to the resource (that is, it must perform a security check) and then typically assert its rights to perform the actual operation.</span></span>

## <a name="related-topics"></a><span data-ttu-id="52b52-152">関連トピック</span><span class="sxs-lookup"><span data-stu-id="52b52-152">Related topics</span></span>

|<span data-ttu-id="52b52-153">タイトル</span><span class="sxs-lookup"><span data-stu-id="52b52-153">Title</span></span>|<span data-ttu-id="52b52-154">説明</span><span class="sxs-lookup"><span data-stu-id="52b52-154">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="52b52-155">状態データの保護</span><span class="sxs-lookup"><span data-stu-id="52b52-155">Securing State Data</span></span>](securing-state-data.md)|<span data-ttu-id="52b52-156">プライベート メンバーを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="52b52-156">Describes how to protect private members.</span></span>|
|[<span data-ttu-id="52b52-157">セキュリティとユーザー入力</span><span class="sxs-lookup"><span data-stu-id="52b52-157">Security and User Input</span></span>](security-and-user-input.md)|<span data-ttu-id="52b52-158">ユーザー入力を受け取るアプリケーションのセキュリティ問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="52b52-158">Describes security concerns for applications that accept user input.</span></span>|
|[<span data-ttu-id="52b52-159">セキュリティと競合状態</span><span class="sxs-lookup"><span data-stu-id="52b52-159">Security and Race Conditions</span></span>](security-and-race-conditions.md)|<span data-ttu-id="52b52-160">コードで競合状態を回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="52b52-160">Describes how to avoid race conditions in your code.</span></span>|
|[<span data-ttu-id="52b52-161">セキュリティと実行時のコード生成</span><span class="sxs-lookup"><span data-stu-id="52b52-161">Security and On-the-Fly Code Generation</span></span>](security-and-on-the-fly-code-generation.md)|<span data-ttu-id="52b52-162">動的なコードを生成するアプリケーションのセキュリティ問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="52b52-162">Describes security concerns for applications that generate dynamic code.</span></span>|
|[<span data-ttu-id="52b52-163">ロールベースのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="52b52-163">Role-Based Security</span></span>](role-based-security.md)|<span data-ttu-id="52b52-164">NET ロール ベースのセキュリティについて詳しく説明し、コードで使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="52b52-164">Describes .NET role-based security in detail and provides instructions for using it in your code.</span></span>|
