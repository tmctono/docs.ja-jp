---
title: 暗号化クラスへのアルゴリズム名の割り当て
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: c76f80273d37f838ca52efd3b8f8c028b76a4d30
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832681"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="4201d-102">暗号化クラスへのアルゴリズム名の割り当て</span><span class="sxs-lookup"><span data-stu-id="4201d-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="4201d-103">4 つの方法が、開発者は、Windows ソフトウェア開発キット (SDK) を使用して暗号化オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4201d-103">There are four ways a developer can create a cryptography object using the Windows Software Development Kit (SDK):</span></span>  
  
- <span data-ttu-id="4201d-104">使用してオブジェクトを作成、**新しい**演算子。</span><span class="sxs-lookup"><span data-stu-id="4201d-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="4201d-105">呼び出して、特定の暗号化アルゴリズムを実装するオブジェクトを作成、**作成**するアルゴリズムの抽象クラスのメソッド。</span><span class="sxs-lookup"><span data-stu-id="4201d-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="4201d-106">呼び出して、特定の暗号化アルゴリズムを実装するオブジェクトを作成、<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="4201d-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="4201d-107">呼び出して、暗号化アルゴリズム (対称ブロック暗号) などのクラスを実装するオブジェクトを作成、**作成**アルゴリズムの種類の抽象クラスのメソッド (など<xref:System.Security.Cryptography.SymmetricAlgorithm>)。</span><span class="sxs-lookup"><span data-stu-id="4201d-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="4201d-108">たとえば、開発者が、一連のバイトの SHA1 ハッシュを計算するとします。</span><span class="sxs-lookup"><span data-stu-id="4201d-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="4201d-109"><xref:System.Security.Cryptography>名前空間には、SHA1 アルゴリズム、1 つの単なるマネージされた実装および CryptoAPI をラップする 1 つの 2 つの実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4201d-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="4201d-110">開発者は特定の SHA1 実装をインスタンス化を選択できます (など、 <xref:System.Security.Cryptography.SHA1Managed>) 呼び出すことによって、**新しい**演算子。</span><span class="sxs-lookup"><span data-stu-id="4201d-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="4201d-111">ただし、クラスは、SHA1 ハッシュ アルゴリズムを実装している限り、共通言語ランタイムがロードするクラス、問題にしない場合、開発者オブジェクトを作成できますを呼び出して、<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="4201d-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4201d-112">このメソッドを呼び出す**System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")** 、SHA1 ハッシュ アルゴリズムの実装を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4201d-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="4201d-113">開発者が呼び出すことができますも**System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** のため、暗号化構成には既定では、.NET Framework に付属しているアルゴリズムの短い名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4201d-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="4201d-114">開発者が呼び出すことができる場合、ハッシュ アルゴリズムを使用する必要はありません、<xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>ハッシュの変換を実装するオブジェクトを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="4201d-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="4201d-115">構成ファイル内のアルゴリズム名のマッピング</span><span class="sxs-lookup"><span data-stu-id="4201d-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="4201d-116">既定では、ランタイムが返されます、 <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> 4 つのシナリオをすべてのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4201d-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="4201d-117">ただし、コンピューターの管理者は、最後の 2 つのシナリオで、メソッドが返すオブジェクトの種類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4201d-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="4201d-118">これを行うには、マシン構成ファイル (Machine.config) で使用するクラスにアルゴリズムの表示名をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4201d-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="4201d-119">次の例は、ランタイムを構成する方法を示しますように**System.Security.Cryptography.SHA1.Create**、 **System.Security.CryptoConfig.CreateFromName("SHA1")** 、および**System.Security.Cryptography.HashAlgorithm.Create**を返す、`MySHA1HashClass`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4201d-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="4201d-120">内の属性の名前を指定することができます、 [< cryptoClass\>要素](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)(前の例では、名前、属性`MySHA1Hash`)。</span><span class="sxs-lookup"><span data-stu-id="4201d-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="4201d-121">内の属性の値、  **\<cryptoClass >** 要素は、共通言語ランタイムを使用して、クラスを検索する文字列。</span><span class="sxs-lookup"><span data-stu-id="4201d-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="4201d-122">指定された要件を満たす任意の文字列を使用する[完全修飾型名の指定](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="4201d-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="4201d-123">さまざまなアルゴリズムの名前は、同じクラスにマップできます。</span><span class="sxs-lookup"><span data-stu-id="4201d-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="4201d-124">[ \<NameEntry > 要素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)クラスを 1 つのアルゴリズムの表示名にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4201d-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="4201d-125">**名前**属性を呼び出すときに使用される文字列を指定できます、 **System.Security.Cryptography.CryptoConfig.CreateFromName**メソッド、または、で抽象暗号化クラスの名前<xref:System.Security.Cryptography>名前空間。</span><span class="sxs-lookup"><span data-stu-id="4201d-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="4201d-126">値、**クラス**属性は、属性の名前、  **\<cryptoClass >** 要素。</span><span class="sxs-lookup"><span data-stu-id="4201d-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4201d-127">SHA1 アルゴリズムを呼び出すことによって取得できます、<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>または**Security.CryptoConfig.CreateFromName("SHA1")** メソッド。</span><span class="sxs-lookup"><span data-stu-id="4201d-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="4201d-128">各メソッドは、SHA1 アルゴリズムを実装するオブジェクトを返すことのみ保証されます。</span><span class="sxs-lookup"><span data-stu-id="4201d-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="4201d-129">構成ファイルで同じクラスに、アルゴリズムのそれぞれの表示名をマップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4201d-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="4201d-130">既定の名前とそれをマッピングするクラスの一覧は、次を参照してください。<xref:System.Security.Cryptography.CryptoConfig>します。</span><span class="sxs-lookup"><span data-stu-id="4201d-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4201d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4201d-131">See also</span></span>

- [<span data-ttu-id="4201d-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4201d-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="4201d-133">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="4201d-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
