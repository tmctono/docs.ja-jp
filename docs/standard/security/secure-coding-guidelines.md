---
title: .NET 用の安全なコーディングのガイドライン
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
ms.openlocfilehash: 51f835803cc545e2a9982c1c8a90d0c998c2bcb8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705913"
---
# <a name="secure-coding-guidelines"></a><span data-ttu-id="ff75c-102">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="ff75c-102">Secure coding guidelines</span></span>

<span data-ttu-id="ff75c-103">エビデンスベース セキュリティとコード アクセス セキュリティは、セキュリティを実現するための強力で明示的なメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-103">Evidence-based security and code access security provide very powerful, explicit mechanisms to implement security.</span></span> <span data-ttu-id="ff75c-104">ほとんどのアプリケーションコードは、.NET によって実装されたインフラストラクチャを単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff75c-104">Most application code can simply use the infrastructure implemented by .NET.</span></span> <span data-ttu-id="ff75c-105">場合によっては、アプリケーション特有の追加のセキュリティが必要になります。これは、セキュリティ システムを拡張するか、または新しい特有の方法を使用して構築されます。</span><span class="sxs-lookup"><span data-stu-id="ff75c-105">In some cases, additional application-specific security is required, built either by extending the security system or by using new ad hoc methods.</span></span>

<span data-ttu-id="ff75c-106">.NET の適用されたアクセス許可とコードのその他の適用を使用して、悪意のあるコードが必要のない情報にアクセスしたり、他の望ましくないアクションを実行したりするのを防ぐために、バリアを課さする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-106">Using .NET enforced permissions and other enforcement in your code, you should erect barriers to prevent malicious code from accessing information that you don't want it to have or performing other undesirable actions.</span></span> <span data-ttu-id="ff75c-107">また、信頼されるコードを使用するすべての想定されるシナリオで、セキュリティと使いやすさのバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-107">Additionally, you must strike a balance between security and usability in all the expected scenarios using trusted code.</span></span>

<span data-ttu-id="ff75c-108">この概要では、セキュリティ システムと連携するようコードを設計するさまざまな方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-108">This overview describes the different ways code can be designed to work with the security system.</span></span>

## <a name="securing-resource-access"></a><span data-ttu-id="ff75c-109">リソースアクセスの保護</span><span class="sxs-lookup"><span data-stu-id="ff75c-109">Securing resource access</span></span>

<span data-ttu-id="ff75c-110">コードを設計して作成する場合、作成元が不明なコードを使用したり呼び出したりする際は特に、コードがリソースに対して持つアクセス権の保護と制限を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-110">When designing and writing your code, you need to protect and limit the access that code has to resources, especially when using or invoking code of unknown origin.</span></span> <span data-ttu-id="ff75c-111">そのため、コードの安全性を確保するために次の点に注意します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-111">So, keep in mind the following techniques to ensure your code is secure:</span></span>

- <span data-ttu-id="ff75c-112">コード アクセス セキュリティ (CAS) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-112">Do not use Code Access Security (CAS).</span></span>

- <span data-ttu-id="ff75c-113">部分的に信頼されたコードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-113">Do not use partial trusted code.</span></span>

- <span data-ttu-id="ff75c-114">[AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute)属性 (APTCA) は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-114">Do not use the [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) attribute (APTCA).</span></span>

- <span data-ttu-id="ff75c-115">.NET リモート処理を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-115">Do not use .NET Remoting.</span></span>

- <span data-ttu-id="ff75c-116">分散コンポーネント オブジェクト モデル (DCOM) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-116">Do not use Distributed Component Object Model (DCOM).</span></span>

- <span data-ttu-id="ff75c-117">バイナリ フォーマッタを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-117">Do not use binary formatters.</span></span>

<span data-ttu-id="ff75c-118">コードアクセスセキュリティと透過的セキュリティコードは、部分的に信頼されたコードを持つセキュリティ境界としてはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ff75c-118">Code Access Security and Security-Transparent Code are not supported as a security boundary with partially trusted code.</span></span> <span data-ttu-id="ff75c-119">発生元の不明なコードの読み込みと実行に関しては、他のセキュリティ対策を適切に導入することなく行わないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-119">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="ff75c-120">代わりのセキュリティ対策は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ff75c-120">The alternative security measures are:</span></span>

- <span data-ttu-id="ff75c-121">仮想化</span><span class="sxs-lookup"><span data-stu-id="ff75c-121">Virtualization</span></span>

- <span data-ttu-id="ff75c-122">AppContainers</span><span class="sxs-lookup"><span data-stu-id="ff75c-122">AppContainers</span></span>

- <span data-ttu-id="ff75c-123">オペレーティング システム (OS) のユーザーおよびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ff75c-123">Operating system (OS) users and permissions</span></span>

- <span data-ttu-id="ff75c-124">Hyper-V コンテナー</span><span class="sxs-lookup"><span data-stu-id="ff75c-124">Hyper-V containers</span></span>

## <a name="security-neutral-code"></a><span data-ttu-id="ff75c-125">セキュリティ中立のコード</span><span class="sxs-lookup"><span data-stu-id="ff75c-125">Security-neutral code</span></span>

<span data-ttu-id="ff75c-126">セキュリティ中立なコードは、セキュリティ システムに対して明示的な操作を何も行いません。</span><span class="sxs-lookup"><span data-stu-id="ff75c-126">Security-neutral code does nothing explicit with the security system.</span></span> <span data-ttu-id="ff75c-127">これは何であれ自分が受け取ったアクセス許可を使用して動作します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-127">It runs with whatever permissions it receives.</span></span> <span data-ttu-id="ff75c-128">保護された操作 (ファイルやネットワークなどの使用など) に関連するセキュリティ例外をキャッチできないアプリケーションでは、ハンドルされない例外が発生する可能性がありますが、セキュリティ中立なコードは .NET のセキュリティテクノロジを利用します.</span><span class="sxs-lookup"><span data-stu-id="ff75c-128">Although applications that fail to catch security exceptions associated with protected operations (such as using files, networking, and so on) can result in an unhandled exception, security-neutral code still takes advantage of the security technologies in .NET.</span></span>

<span data-ttu-id="ff75c-129">セキュリティ中立なライブラリは、理解しておくべき特別な特性を持っています。</span><span class="sxs-lookup"><span data-stu-id="ff75c-129">A security-neutral library has special characteristics that you should understand.</span></span> <span data-ttu-id="ff75c-130">ファイルを使用したり、アンマネージコードを呼び出したりする API 要素がライブラリに用意されているとします。</span><span class="sxs-lookup"><span data-stu-id="ff75c-130">Suppose your library provides API elements that use files or call unmanaged code.</span></span> <span data-ttu-id="ff75c-131">コードに対応するアクセス許可がない場合は、説明どおりに実行されません。</span><span class="sxs-lookup"><span data-stu-id="ff75c-131">If your code doesn't have the corresponding permission, it won't run as described.</span></span> <span data-ttu-id="ff75c-132">しかし、コードがアクセス許可を持っているとしても、そのコードを呼び出すアプリケーション コードが同じアクセス許可を持っていなければ、正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="ff75c-132">However, even if the code has the permission, any application code that calls it must have the same permission in order to work.</span></span> <span data-ttu-id="ff75c-133">呼び出し元のコードに適切なアクセス許可がない場合は、コードアクセスセキュリティスタックウォークの結果として <xref:System.Security.SecurityException> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff75c-133">If the calling code doesn't have the right permission, a <xref:System.Security.SecurityException> appears as a result of the code access security stack walk.</span></span>

## <a name="application-code-that-isnt-a-reusable-component"></a><span data-ttu-id="ff75c-134">再利用可能なコンポーネントではないアプリケーションコード</span><span class="sxs-lookup"><span data-stu-id="ff75c-134">Application code that isn't a reusable component</span></span>

<span data-ttu-id="ff75c-135">コードが他のコードによって呼び出されないアプリケーションの一部である場合、セキュリティは単純であり、特殊なコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ff75c-135">If your code is part of an application that won't be called by other code, security is simple and special coding might not be required.</span></span> <span data-ttu-id="ff75c-136">ただし、悪意のあるコードがそのコードを呼び出す可能性があることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="ff75c-136">However, remember that malicious code can call your code.</span></span> <span data-ttu-id="ff75c-137">悪意のあるコードによるリソースへのアクセスをコード アクセス セキュリティが阻止する可能性もありますが、機密情報を含んだフィールドやプロパティの値をそのようなコードが読み取ることも考えられます。</span><span class="sxs-lookup"><span data-stu-id="ff75c-137">While code access security might stop malicious code from accessing resources, such code could still read values of your fields or properties that might contain sensitive information.</span></span>

<span data-ttu-id="ff75c-138">また、コードがインターネットやその他の信頼できないソースからのユーザー入力を受け付ける場合には、悪意のある入力にも注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-138">Additionally, if your code accepts user input from the Internet or other unreliable sources, you must be careful about malicious input.</span></span>

## <a name="managed-wrapper-to-native-code-implementation"></a><span data-ttu-id="ff75c-139">マネージラッパーからネイティブコードへの実装</span><span class="sxs-lookup"><span data-stu-id="ff75c-139">Managed wrapper to native code implementation</span></span>

<span data-ttu-id="ff75c-140">一般にこのシナリオは、何らかの有用な機能がネイティブ コードで実装されており、これをマネージド コードで利用したいというケースに該当します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-140">Typically in this scenario, some useful functionality is implemented in native code that you want to make available to managed code.</span></span> <span data-ttu-id="ff75c-141">マネージド ラッパーは、プラットフォーム呼び出しか COM 相互運用を使用して簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff75c-141">Managed wrappers are easy to write using either platform invoke or COM interop.</span></span> <span data-ttu-id="ff75c-142">ただしこの場合には、操作を成功させるために、ラッパーの呼び出し元がアンマネージ コードの権利を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-142">However, if you do this, callers of your wrappers must have unmanaged code rights in order to succeed.</span></span> <span data-ttu-id="ff75c-143">既定のポリシーでは、イントラネットまたはインターネットからダウンロードされたコードがラッパーで動作しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-143">Under default policy, this means that code downloaded from an intranet or the Internet won't work with the wrappers.</span></span>

<span data-ttu-id="ff75c-144">これらのラッパーを使用するすべてのアプリケーションにアンマネージコード権限を付与するのではなく、ラッパーコードにのみこれらの権限を付与することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ff75c-144">Instead of giving unmanaged code rights to all applications that use these wrappers, it's better to give these rights only to the wrapper code.</span></span> <span data-ttu-id="ff75c-145">基になる機能が何もリソースを公開しておらず、かつ実装も同様に安全である場合、ラッパーは、自分の権利をアサートしさえすれば、あらゆるコードが自分を通して呼び出しを行えるようにできます。</span><span class="sxs-lookup"><span data-stu-id="ff75c-145">If the underlying functionality exposes no resources and the implementation is likewise safe, the wrapper only needs to assert its rights, which enables any code to call through it.</span></span> <span data-ttu-id="ff75c-146">リソースが関係する場合のセキュリティ コーディングは、次のセクションで説明するライブラリ コードのケースと同じです。</span><span class="sxs-lookup"><span data-stu-id="ff75c-146">When resources are involved, security coding should be the same as the library code case described in the next section.</span></span> <span data-ttu-id="ff75c-147">ラッパーはこれらのリソースに対して呼び出し元を公開する可能性があるため、ネイティブ コードの安全性を慎重に確認する必要があり、その責任はラッパーにあります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-147">Because the wrapper is potentially exposing callers to these resources, careful verification of the safety of the native code is necessary and is the wrapper's responsibility.</span></span>

## <a name="library-code-that-exposes-protected-resources"></a><span data-ttu-id="ff75c-148">保護されたリソースを公開するライブラリコード</span><span class="sxs-lookup"><span data-stu-id="ff75c-148">Library code that exposes protected resources</span></span>

<span data-ttu-id="ff75c-149">次の方法は、最も強力であり、セキュリティコーディングのために (正しく完了していない場合に) 危険に陥る可能性があります。 .NET クラスが適用する場合と同様に、使用できない特定のリソースにアクセスするために、ライブラリは他のコードのインターフェイスとして機能します。使用するリソースのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="ff75c-149">The following approach is the most powerful and hence potentially dangerous (if done incorrectly) for security coding: your library serves as an interface for other code to access certain resources that aren't otherwise available, just as the .NET classes enforce permissions for the resources they use.</span></span> <span data-ttu-id="ff75c-150">どこでリソースを公開しようと、コードはまずそのリソースに適したアクセス許可を要求し (つまりセキュリティ チェックを実行しなければなりません)、それから通常は実際の操作を実行するための権利をアサートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff75c-150">Wherever you expose a resource, your code must first demand the permission appropriate to the resource (that is, it must perform a security check) and then typically assert its rights to perform the actual operation.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff75c-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff75c-151">Related topics</span></span>

|<span data-ttu-id="ff75c-152">[タイトル]</span><span class="sxs-lookup"><span data-stu-id="ff75c-152">Title</span></span>|<span data-ttu-id="ff75c-153">説明</span><span class="sxs-lookup"><span data-stu-id="ff75c-153">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="ff75c-154">状態データの保護</span><span class="sxs-lookup"><span data-stu-id="ff75c-154">Securing State Data</span></span>](securing-state-data.md)|<span data-ttu-id="ff75c-155">プライベート メンバーを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-155">Describes how to protect private members.</span></span>|
|[<span data-ttu-id="ff75c-156">セキュリティとユーザー入力</span><span class="sxs-lookup"><span data-stu-id="ff75c-156">Security and User Input</span></span>](security-and-user-input.md)|<span data-ttu-id="ff75c-157">ユーザー入力を受け取るアプリケーションのセキュリティ問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-157">Describes security concerns for applications that accept user input.</span></span>|
|[<span data-ttu-id="ff75c-158">セキュリティと競合状態</span><span class="sxs-lookup"><span data-stu-id="ff75c-158">Security and Race Conditions</span></span>](security-and-race-conditions.md)|<span data-ttu-id="ff75c-159">コードで競合状態を回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-159">Describes how to avoid race conditions in your code.</span></span>|
|[<span data-ttu-id="ff75c-160">セキュリティと実行時のコード生成</span><span class="sxs-lookup"><span data-stu-id="ff75c-160">Security and On-the-Fly Code Generation</span></span>](security-and-on-the-fly-code-generation.md)|<span data-ttu-id="ff75c-161">動的なコードを生成するアプリケーションのセキュリティ問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-161">Describes security concerns for applications that generate dynamic code.</span></span>|
|[<span data-ttu-id="ff75c-162">ロール ベースのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ff75c-162">Role-Based Security</span></span>](role-based-security.md)|<span data-ttu-id="ff75c-163">.NET のロールベースセキュリティについて詳しく説明し、コードで使用するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ff75c-163">Describes .NET role-based security in detail and provides instructions for using it in your code.</span></span>|
