---
title: コード アクセス セキュリティの基礎
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], code access security
ms.assetid: 4eaa6535-d9fe-41a1-91d8-b437cfc16921
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bbf97b3bc72a12f8920e3a3cace3f7c31ed1e71a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910981"
---
# <a name="code-access-security-basics"></a><span data-ttu-id="d8f9a-102">コード アクセス セキュリティの基礎</span><span class="sxs-lookup"><span data-stu-id="d8f9a-102">Code Access Security Basics</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="d8f9a-103">共通言語ランタイムに対応するすべてのアプリケーション (つまりすべてのマネージド アプリケーション) は、そのランタイムのセキュリティ システムと対話する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-103">Every application that targets the common language runtime (that is, every managed application) must interact with the runtime's security system.</span></span> <span data-ttu-id="d8f9a-104">マネージ アプリケーションのホストは、そのアプリケーションの起動時に、アプリケーションに対して一連のアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-104">When a managed application is loaded, its host automatically grants it a set of permissions.</span></span> <span data-ttu-id="d8f9a-105">これらのアクセス許可は、ホストのローカル セキュリティ設定、またはアプリケーションが所属するサンドボックスによって決まります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-105">These permissions are determined by the host's local security settings or by the sandbox the application is in.</span></span> <span data-ttu-id="d8f9a-106">これらのアクセス許可に応じて、そのアプリケーションが正常に実行されるか、またはセキュリティ例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-106">Depending on these permissions, the application either runs properly or generates a security exception.</span></span>

<span data-ttu-id="d8f9a-107">デスクトップ アプリケーションの既定のホストでは、コードが完全な信頼を付与されて実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-107">The default host for desktop applications allows code to run in full trust.</span></span> <span data-ttu-id="d8f9a-108">このため、アプリケーションの実行対象がデスクトップである場合は、アプリケーションに無制限のアクセス許可セットが付与されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-108">Therefore, if your application targets the desktop, it has an unrestricted permission set.</span></span> <span data-ttu-id="d8f9a-109">その他のホストまたはサンドボックスでは、アプリケーションに対して制限付きのアクセス許可セットが付与されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-109">Other hosts or sandboxes provide a limited permission set for applications.</span></span> <span data-ttu-id="d8f9a-110">アクセス許可セットはホストごとに異なる場合があるため、アプリケーションの設計時には、対象ホストで許可されているアクセス許可だけを使用するように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-110">Because the permission set can change from host to host, you must design your application to use only the permissions that your target host allows.</span></span>

<span data-ttu-id="d8f9a-111">共通言語ランタイムに対応した有効なアプリケーションを作成するためには、次に示すコード アクセス セキュリティの概念を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-111">You must be familiar with the following code access security concepts in order to write effective applications that target the common language runtime:</span></span>

- <span data-ttu-id="d8f9a-112">**タイプセーフなコード**:タイプセーフなコードとは、適切に定義された許可された方法でのみ型にアクセスするコードのことです。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-112">**Type-safe code**: Type-safe code is code that accesses types only in well-defined, allowable ways.</span></span> <span data-ttu-id="d8f9a-113">たとえば、有効なオブジェクト参照を例として考えると、タイプ セーフ コードは、実際のフィールド メンバーに対応する固定オフセットが指すメモリ位置にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-113">For example, given a valid object reference, type-safe code can access memory at fixed offsets that correspond to actual field members.</span></span> <span data-ttu-id="d8f9a-114">オブジェクトがパブリックに公開するフィールドに属しているメモリの範囲外の、任意のオフセットが指すメモリ位置にアクセスするコードは、タイプ セーフとは言えません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-114">If the code accesses memory at arbitrary offsets outside the range of memory that belongs to that object's publicly exposed fields, it is not type-safe.</span></span> <span data-ttu-id="d8f9a-115">コードがコード アクセス セキュリティを活用できるようにするには、検証可能なタイプ セーフ コードを生成するコンパイラを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-115">To enable code to benefit from code access security, you must use a compiler that generates verifiably type-safe code.</span></span> <span data-ttu-id="d8f9a-116">詳細については、このトピックで後述する「検証可能[なタイプセーフコードの作成](#typesafe_code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-116">For more information, see the [Writing Verifiably Type-Safe Code](#typesafe_code) section later in this topic.</span></span>

- <span data-ttu-id="d8f9a-117">**命令型および宣言型の構文**:共通言語ランタイムを対象とするコードは、アクセス許可を要求し、呼び出し元が指定したアクセス許可を持つことを要求し、特定のセキュリティ設定 (十分な特権が与えられている場合) をオーバーライドすることによって、セキュリティシステムと対話できます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-117">**Imperative and declarative syntax**: Code that targets the common language runtime can interact with the security system by requesting permissions, demanding that callers have specified permissions, and overriding certain security settings (given enough privileges).</span></span> <span data-ttu-id="d8f9a-118">.NET Framework セキュリティ システムとプログラムによって対話するには、宣言構文および強制構文という 2 つの形式の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-118">You use two forms of syntax to programmatically interact with the .NET Framework security system: declarative syntax and imperative syntax.</span></span> <span data-ttu-id="d8f9a-119">宣言的な呼び出しは属性を使用して実行され、強制的な呼び出しはコード内のクラスの新しいインスタンスを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-119">Declarative calls are performed using attributes; imperative calls are performed using new instances of classes within your code.</span></span> <span data-ttu-id="d8f9a-120">呼び出しには、強制的にだけ実行できるもの、宣言的にだけ実行できるもの、およびどちらの方法でも実行できるものがあります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-120">Some calls can be performed only imperatively, others can be performed only declaratively, and some calls can be performed in either manner.</span></span>

- <span data-ttu-id="d8f9a-121">**セキュリティで保護されたクラスライブラリ**:安全なクラスライブラリは、セキュリティ要求を使用して、ライブラリの呼び出し元が、ライブラリが公開するリソースにアクセスするためのアクセス許可を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-121">**Secure class libraries**: A secure class library uses security demands to ensure that the library's callers have permission to access the resources that the library exposes.</span></span> <span data-ttu-id="d8f9a-122">たとえば、安全なクラス ライブラリにファイルを作成するメソッドがある場合、このメソッドにアクセスする呼び出し元には、ファイルを作成するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-122">For example, a secure class library might have a method for creating files that would demand that its callers have permissions to create files.</span></span> <span data-ttu-id="d8f9a-123">.NET Framework は、安全なクラス ライブラリで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-123">The .NET Framework consists of secure class libraries.</span></span> <span data-ttu-id="d8f9a-124">作成するコードで使用するすべてのライブラリについて、アクセスするために必要なアクセス許可を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-124">You should be aware of the permissions required to access any library that your code uses.</span></span> <span data-ttu-id="d8f9a-125">詳細については、このトピックの後半の「[セキュリティで保護されたクラスライブラリの使用](#secure_library)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-125">For more information, see the [Using Secure Class Libraries](#secure_library) section later in this topic.</span></span>

- <span data-ttu-id="d8f9a-126">**透過的なコード**:.NET Framework 4 以降では、特定のアクセス許可を識別するだけでなく、コードを透過的セキュリティとして実行するかどうかも決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-126">**Transparent code**: Starting with the .NET Framework 4, in addition to identifying specific permissions, you must also determine whether your code should run as security-transparent.</span></span> <span data-ttu-id="d8f9a-127">セキュリティ透過コードは、セキュリティが重要な型またはメンバーを呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-127">Security-transparent code cannot call types or members that are identified as security-critical.</span></span> <span data-ttu-id="d8f9a-128">この規則は、完全に信頼されているアプリケーションと、部分的に信頼されたアプリケーションの両方に対して適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-128">This rule applies to full-trust applications as well as partially trusted applications.</span></span> <span data-ttu-id="d8f9a-129">詳細については、「[透過的セキュリティコード](../../../docs/framework/misc/security-transparent-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-129">For more information, see [Security-Transparent Code](../../../docs/framework/misc/security-transparent-code.md).</span></span>

<a name="typesafe_code"></a>

## <a name="writing-verifiably-type-safe-code"></a><span data-ttu-id="d8f9a-130">検証可能なタイプ セーフ コードの作成</span><span class="sxs-lookup"><span data-stu-id="d8f9a-130">Writing Verifiably Type-Safe Code</span></span>

<span data-ttu-id="d8f9a-131">JIT (Just-in-time) コンパイルでは、検証プロセスが実行され、コードが調べられてタイプ セーフかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-131">Just-in-time (JIT) compilation performs a verification process that examines code and tries to determine whether the code is type-safe.</span></span> <span data-ttu-id="d8f9a-132">検証中にタイプセーフであることが実証されたコードは、検証可能な*タイプセーフコード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-132">Code that is proven during verification to be type-safe is called *verifiably type-safe code*.</span></span> <span data-ttu-id="d8f9a-133">検証プロセスやコンパイラに制約があるために検証可能なタイプ セーフ コードではなくても、コードがタイプ セーフである場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-133">Code can be type-safe, yet might not be verifiably type-safe because of the limitations of the verification process or of the compiler.</span></span> <span data-ttu-id="d8f9a-134">タイプ セーフではない言語もあり、Microsoft Visual C++ などの一部の言語コンパイラは、検証可能なタイプ セーフ マネージ コードを生成できません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-134">Not all languages are type-safe, and some language compilers, such as Microsoft Visual C++, cannot generate verifiably type-safe managed code.</span></span> <span data-ttu-id="d8f9a-135">使用している言語コンパイラが検証可能なタイプ セーフ コードを生成するかどうかを確認するには、そのコンパイラのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-135">To determine whether the language compiler you use generates verifiably type-safe code, consult the compiler's documentation.</span></span> <span data-ttu-id="d8f9a-136">特定の言語構成要素を使用しない場合にのみ検証可能なタイプセーフコードを生成する言語コンパイラを使用する場合は、 [PEVerify ツール](../../../docs/framework/tools/peverify-exe-peverify-tool.md)を使用して、コードが検証可能なタイプセーフであるかどうかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-136">If you use a language compiler that generates verifiably type-safe code only when you avoid certain language constructs, you might want to use the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md) to determine whether your code is verifiably type-safe.</span></span>

<span data-ttu-id="d8f9a-137">検証可能なタイプ セーフ コード以外のコードは、セキュリティ ポリシーによって検証を省略することを許可されている場合にだけ、実行を試行できます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-137">Code that is not verifiably type-safe can attempt to execute if security policy allows the code to bypass verification.</span></span> <span data-ttu-id="d8f9a-138">ただし、タイプ セーフは、アセンブリを分離するためのランタイムの機構において重要な要素であるため、コードがタイプ セーフの規則に違反している場合には、信頼度の高いセキュリティを確保することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-138">However, because type safety is an essential part of the runtime's mechanism for isolating assemblies, security cannot be reliably enforced if code violates the rules of type safety.</span></span> <span data-ttu-id="d8f9a-139">既定では、タイプ セーフでないコードは、その発生元がローカル コンピューターである場合にだけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-139">By default, code that is not type-safe is allowed to run only if it originates from the local computer.</span></span> <span data-ttu-id="d8f9a-140">したがって、モバイル コードはタイプ セーフであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-140">Therefore, mobile code should be type-safe.</span></span>

<a name="secure_library"></a>

## <a name="using-secure-class-libraries"></a><span data-ttu-id="d8f9a-141">安全なクラス ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="d8f9a-141">Using Secure Class Libraries</span></span>

<span data-ttu-id="d8f9a-142">作成したコードが、クラス ライブラリにより要求されるアクセス許可を要求し、そのアクセス許可を与えられた場合には、そのコードからライブラリにアクセスでき、ライブラリが公開するリソースは承認されていないアクセスから保護されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-142">If your code requests and is granted the permissions required by the class library, it will be allowed to access the library and the resources that the library exposes will be protected from unauthorized access.</span></span> <span data-ttu-id="d8f9a-143">コードが適切なアクセス許可を持っていない場合には、そのコードはクラス ライブラリにアクセスできないため、悪意のあるコードがそのコードを利用して保護されたリソースに間接的にアクセスすることもできません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-143">If your code does not have the appropriate permissions, it will not be allowed to access the class library, and malicious code will not be able to use your code to indirectly access protected resources.</span></span> <span data-ttu-id="d8f9a-144">作成したコードを呼び出す他のコードも、ライブラリへのアクセス許可が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-144">Other code that calls your code must also have permission to access the library.</span></span> <span data-ttu-id="d8f9a-145">アクセス許可がない場合は、作成したコードの実行も制限されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-145">If it does not, your code will be restricted from running as well.</span></span>

<span data-ttu-id="d8f9a-146">コード アクセス セキュリティを使用しても開発者によるコードの記述エラーがなくなるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-146">Code access security does not eliminate the possibility of human error in writing code.</span></span> <span data-ttu-id="d8f9a-147">ただし、保護されているリソースにアクセスするときにアプリケーションが安全なクラス ライブラリを使用していれば、クラス ライブラリでセキュリティの問題が発生する可能性がないかどうかが詳しく調べられるため、アプリケーション コードに対するセキュリティ リスクも軽減されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-147">However, if your application uses secure class libraries to access protected resources, the security risk for application code is decreased, because class libraries are closely scrutinized for potential security problems.</span></span>

## <a name="declarative-security"></a><span data-ttu-id="d8f9a-148">宣言セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d8f9a-148">Declarative Security</span></span>

<span data-ttu-id="d8f9a-149">宣言セキュリティ構文では、[属性](../../standard/attributes/index.md)を使用して、コードの[メタデータ](../../standard/metadata-and-self-describing-components.md)にセキュリティ情報を配置します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-149">Declarative security syntax uses [attributes](../../standard/attributes/index.md) to place security information into the [metadata](../../standard/metadata-and-self-describing-components.md) of your code.</span></span> <span data-ttu-id="d8f9a-150">属性は、アセンブリ、クラス、またはメンバーの各レベルに適用でき、使用する要求、確認要求、オーバーライドの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-150">Attributes can be placed at the assembly, class, or member level, to indicate the type of request, demand, or override you want to use.</span></span> <span data-ttu-id="d8f9a-151">要求は、共通言語ランタイムに対応するアプリケーションが、そのアプリケーションに必要なアクセス許可または必要ではないアクセス許可をランタイムのセキュリティ システムに通知するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-151">Requests are used in applications that target the common language runtime to inform the runtime security system about the permissions that your application needs or does not want.</span></span> <span data-ttu-id="d8f9a-152">確認要求およびオーバーライドは、呼び出し元からリソースを保護できるようにしたり、既定のセキュリティ動作をオーバーライドしたりするために、ライブラリで使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-152">Demands and overrides are used in libraries to help protect resources from callers or to override default security behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="d8f9a-153">.NET Framework 4 では、.NET Framework セキュリティモデルと用語に重要な変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-153">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="d8f9a-154">これらの変更の詳細については、「[セキュリティの変更](../../../docs/framework/security/security-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-154">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>

<span data-ttu-id="d8f9a-155">宣言セキュリティ呼び出しを行う前に、アクセス許可オブジェクトの状態データを、必要な特定形式のアクセス許可を表すように初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-155">In order to use declarative security calls, you must initialize the state data of the permission object so that it represents the particular form of permission you need.</span></span> <span data-ttu-id="d8f9a-156">組み込みの各アクセス許可は、開発者が実行するセキュリティ操作の種類を示す <xref:System.Security.Permissions.SecurityAction> 列挙として渡される属性を持っています。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-156">Every built-in permission has an attribute that is passed a <xref:System.Security.Permissions.SecurityAction> enumeration to describe the type of security operation you want to perform.</span></span> <span data-ttu-id="d8f9a-157">しかし、アクセス許可は、それぞれに固有のパラメーターも受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-157">However, permissions also accept their own parameters that are exclusive to them.</span></span>

<span data-ttu-id="d8f9a-158">コードの呼び出し元がカスタム アクセス許可 `MyPermission` を持つことを要求する宣言構文の例を次のコード片に示します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-158">The following code fragment shows declarative syntax for requesting that your code's callers have a custom permission called `MyPermission`.</span></span> <span data-ttu-id="d8f9a-159">このアクセス許可は架空のカスタム許可であり、.NET Framework には実在しません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-159">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="d8f9a-160">この例では、宣言呼び出しはクラス定義の直前に配置されており、このカスタム アクセス許可がクラス レベルで適用されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-160">In this example, the declarative call is placed directly before the class definition, specifying that this permission be applied to the class level.</span></span> <span data-ttu-id="d8f9a-161">属性には**SecurityAction**構造体が渡され、呼び出し元が実行のためにこのアクセス許可を持っている必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-161">The attribute is passed a **SecurityAction.Demand** structure to specify that callers must have this permission in order to run.</span></span>

```vb
<MyPermission(SecurityAction.Demand, Unrestricted = True)> Public Class MyClass1

   Public Sub New()
      'The constructor is protected by the security call.
   End Sub

   Public Sub MyMethod()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'This method is protected by the security call.
   End Sub
End Class
```

```csharp
[MyPermission(SecurityAction.Demand, Unrestricted = true)]
public class MyClass
{
   public MyClass()
   {
      //The constructor is protected by the security call.
   }

   public void MyMethod()
   {
      //This method is protected by the security call.
   }

   public void YourMethod()
   {
      //This method is protected by the security call.
   }
}
```

## <a name="imperative-security"></a><span data-ttu-id="d8f9a-162">強制セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d8f9a-162">Imperative Security</span></span>

<span data-ttu-id="d8f9a-163">強制セキュリティ構文は、呼び出す対象のアクセス許可オブジェクトの新しいインスタンスを作成することによって、セキュリティ呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-163">Imperative security syntax issues a security call by creating a new instance of the permission object you want to invoke.</span></span> <span data-ttu-id="d8f9a-164">強制構文を使用して確認要求とオーバーライドは実行できますが、要求は実行できません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-164">You can use imperative syntax to perform demands and overrides, but not requests.</span></span>

<span data-ttu-id="d8f9a-165">セキュリティ呼び出しを行う前に、アクセス許可オブジェクトの状態データを、必要な特定形式のアクセス許可を表すように初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-165">Before you make the security call, you must initialize the state data of the permission object so that it represents the particular form of the permission you need.</span></span> <span data-ttu-id="d8f9a-166">たとえば、 <xref:System.Security.Permissions.FileIOPermission>オブジェクトを作成するときに、コンストラクターを使用して、すべてのファイルへの無制限のアクセスまたはファイルへのアクセスが許可されないように、 **FileIOPermission**オブジェクトを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-166">For example, when creating a <xref:System.Security.Permissions.FileIOPermission> object, you can use the constructor to initialize the **FileIOPermission** object so that it represents either unrestricted access to all files or no access to files.</span></span> <span data-ttu-id="d8f9a-167">または、別の**FileIOPermission**オブジェクトを使用して、オブジェクトが表すアクセスの種類 (つまり、読み取り、追加、または書き込み) と、オブジェクトで保護するファイルを指定するパラメーターを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-167">Or, you can use a different **FileIOPermission** object, passing parameters that indicate the type of access you want the object to represent (that is, read, append, or write) and what files you want the object to protect.</span></span>

<span data-ttu-id="d8f9a-168">強制セキュリティ構文は、単一のセキュリティ オブジェクトを呼び出す他に、アクセス許可セット内のアクセス許可のグループを初期化するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-168">In addition to using imperative security syntax to invoke a single security object, you can use it to initialize a group of permissions in a permission set.</span></span> <span data-ttu-id="d8f9a-169">たとえば、この方法は、1つのメソッドで複数のアクセス許可に対して[アサート](../../../docs/framework/misc/using-the-assert-method.md)呼び出しを確実に実行する唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-169">For example, this technique is the only way to reliably perform [assert](../../../docs/framework/misc/using-the-assert-method.md) calls on multiple permissions in one method.</span></span> <span data-ttu-id="d8f9a-170">それには、<xref:System.Security.PermissionSet> クラスと <xref:System.Security.NamedPermissionSet> クラスを使用して、アクセス許可のグループを作成し、適切なメソッドを呼び出して必要なセキュリティ呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-170">Use the <xref:System.Security.PermissionSet> and <xref:System.Security.NamedPermissionSet> classes to create a group of permissions and then call the appropriate method to invoke the desired security call.</span></span>

<span data-ttu-id="d8f9a-171">強制構文を使用して確認要求とオーバーライドは実行できますが、要求は実行できません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-171">You can use imperative syntax to perform demands and overrides, but not requests.</span></span> <span data-ttu-id="d8f9a-172">アクセス許可の状態を初期化するために必要な情報を実行時にしか取得できない場合には、確認要求やオーバーライドを実行するときに、宣言構文の代わりに強制構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-172">You might use imperative syntax for demands and overrides instead of declarative syntax when information that you need in order to initialize the permission state becomes known only at run time.</span></span> <span data-ttu-id="d8f9a-173">たとえば、呼び出し元に特定のファイルを読み取るためのアクセス許可が必要である場合に、読み取り対象のファイルの名前が実行時までわからないときには、強制確認要求を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-173">For example, if you want to ensure that callers have permission to read a certain file, but you do not know the name of that file until run time, use an imperative demand.</span></span> <span data-ttu-id="d8f9a-174">また、条件を適用するかどうか、およびテストの結果に基づいてセキュリティ確認要求を実行するかどうかを実行時に決定する必要がある場合にも、宣言チェックの代わりに強制チェックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-174">You might also choose to use imperative checks instead of declarative checks when you need to determine at run time whether a condition holds and, based on the result of the test, make a security demand (or not).</span></span>

<span data-ttu-id="d8f9a-175">コードの呼び出し元がカスタム アクセス許可 `MyPermission` を持つことを要求する強制構文の例を次のコード片に示します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-175">The following code fragment shows imperative syntax for requesting that your code's callers have a custom permission called `MyPermission`.</span></span> <span data-ttu-id="d8f9a-176">このアクセス許可は架空のカスタム許可であり、.NET Framework には実在しません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-176">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="d8f9a-177">`MyPermission` の新しいインスタンスが `MyMethod` で生成され、このメソッドだけをセキュリティ呼び出しで保護します。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-177">A new instance of `MyPermission` is created in `MyMethod`, guarding only this method with the security call.</span></span>

```vb
Public Class MyClass1

   Public Sub New()

   End Sub

   Public Sub MyMethod()
      'MyPermission is demanded using imperative syntax.
      Dim Perm As New MyPermission()
      Perm.Demand()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'YourMethod 'This method is not protected by the security call.
   End Sub
End Class
```

```csharp
public class MyClass {
   public MyClass(){

   }

   public void MyMethod() {
       //MyPermission is demanded using imperative syntax.
       MyPermission Perm = new MyPermission();
       Perm.Demand();
       //This method is protected by the security call.
   }

   public void YourMethod() {
       //This method is not protected by the security call.
   }
}
```

## <a name="using-managed-wrapper-classes"></a><span data-ttu-id="d8f9a-178">マネージ ラッパー クラスの使用</span><span class="sxs-lookup"><span data-stu-id="d8f9a-178">Using Managed Wrapper Classes</span></span>

<span data-ttu-id="d8f9a-179">ほとんどのアプリケーションおよびコンポーネント (安全なライブラリ以外) では、アンマネージ コードを直接呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-179">Most applications and components (except secure libraries) should not directly call unmanaged code.</span></span> <span data-ttu-id="d8f9a-180">直接呼び出すべきではないいくつかの理由があります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-180">There are several reasons for this.</span></span> <span data-ttu-id="d8f9a-181">コードによってアンマネージ コードが直接呼び出されると、多くの状況では実行が許可されません。コードでは、ネイティブ コードを呼び出すための高い信頼レベルが付与されていなければならないためです。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-181">If code calls unmanaged code directly, it will not be allowed to run in many circumstances because code must be granted a high level of trust to call native code.</span></span> <span data-ttu-id="d8f9a-182">ポリシーに変更が加えられ、こうしたアプリケーションの実行が許可される場合、アプリケーションではほとんどすべての操作を自由に実行できるようになり、システムのセキュリティがかなり脆弱になる恐れがあります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-182">If policy is modified to allow such an application to run, it can significantly weaken the security of the system, leaving the application free to perform almost any operation.</span></span>

<span data-ttu-id="d8f9a-183">さらに、アンマネージ コードにアクセスできるアクセス許可があるコードは、アンマネージ API を呼び出すことによってほとんどすべての操作を実行できるようになる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-183">Additionally, code that has permission to access unmanaged code can probably perform almost any operation by calling into an unmanaged API.</span></span> <span data-ttu-id="d8f9a-184">たとえば、アンマネージコードを呼び出すためのアクセス許可を持つ<xref:System.Security.Permissions.FileIOPermission>コードは、ファイルにアクセスする必要はありません。アンマネージ (Win32) ファイル api を直接呼び出すだけで、 **FileIOPermission**を必要とするマネージファイル api をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-184">For example, code that has permission to call unmanaged code does not need <xref:System.Security.Permissions.FileIOPermission> to access a file; it can just call an unmanaged (Win32) file API directly, bypassing the managed file API that requires **FileIOPermission**.</span></span> <span data-ttu-id="d8f9a-185">マネージド コードにアンマネージド コードを呼び出すアクセス許可があり、アンマネージド コードを実際に直接呼び出す場合、セキュリティ システムでは、ランタイムがアンマネージド コードに確実な制限を課すことができないため、セキュリティ制限の適用に信頼性が欠けることになります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-185">If managed code has permission to call into unmanaged code and does call directly into unmanaged code, the security system will be unable to reliably enforce security restrictions, since the runtime cannot enforce such restrictions on unmanaged code.</span></span>

<span data-ttu-id="d8f9a-186">アンマネージ コードにアクセスすることが必要な操作をアプリケーションで実行する場合、必要な機能 をラップする信頼できるマネージ クラス (存在する場合) を使用してそうした操作をアプリケーションで実行しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-186">If you want your application to perform an operation that requires accessing unmanaged code, it should do so through a trusted managed class that wraps the required functionality (if such a class exists).</span></span> <span data-ttu-id="d8f9a-187">安全なクラス ライブラリ内のラッパー クラスが既に存在する場合には、独自にラッパー クラスを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-187">Do not create a wrapper class yourself if one already exists in a secure class library.</span></span> <span data-ttu-id="d8f9a-188">ラッパー クラスでは、アンマネージ コードへの呼び出しが許可されるように高度な信頼が付与される必要があります。呼び出し元に適切なアクセス許可があることを確認要求する責任はラッパー クラスにあります。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-188">The wrapper class, which must be granted a high degree of trust to be allowed to make the call into unmanaged code, is responsible for demanding that its callers have the appropriate permissions.</span></span> <span data-ttu-id="d8f9a-189">ラッパー クラスを使用する場合、作成したコードで必要となるのは、ラッパー クラスが確認要求するアクセス許可を要求して付与することのみです。</span><span class="sxs-lookup"><span data-stu-id="d8f9a-189">If you use the wrapper class, your code only needs to request and be granted the permissions that the wrapper class demands.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8f9a-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f9a-190">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.NamedPermissionSet>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="d8f9a-191">Assert</span><span class="sxs-lookup"><span data-stu-id="d8f9a-191">Assert</span></span>](../../../docs/framework/misc/using-the-assert-method.md)
- [<span data-ttu-id="d8f9a-192">コード アクセス セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d8f9a-192">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
- [<span data-ttu-id="d8f9a-193">コード アクセス セキュリティの基礎</span><span class="sxs-lookup"><span data-stu-id="d8f9a-193">Code Access Security Basics</span></span>](../../../docs/framework/misc/code-access-security-basics.md)
- [<span data-ttu-id="d8f9a-194">属性</span><span class="sxs-lookup"><span data-stu-id="d8f9a-194">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="d8f9a-195">メタデータと自己言及的なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8f9a-195">Metadata and Self-Describing Components</span></span>](../../standard/metadata-and-self-describing-components.md)
