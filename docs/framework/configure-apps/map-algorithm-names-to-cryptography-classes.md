---
title: 暗号化クラスへのアルゴリズム名の割り当て
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912863"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="c9d9b-102">暗号化クラスへのアルゴリズム名の割り当て</span><span class="sxs-lookup"><span data-stu-id="c9d9b-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="c9d9b-103">Windows SDK を使用して、開発者が暗号化オブジェクトを作成するには、次の4つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-103">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="c9d9b-104">**New**演算子を使用してオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="c9d9b-105">特定の暗号化アルゴリズムを実装するオブジェクトを作成するには、そのアルゴリズムの抽象クラスで**create**メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="c9d9b-106"><xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>メソッドを呼び出して、特定の暗号化アルゴリズムを実装するオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="c9d9b-107">アルゴリズムの種類 ( <xref:System.Security.Cryptography.SymmetricAlgorithm>など) の抽象クラスで**create**メソッドを呼び出すことによって、暗号アルゴリズムのクラス (対称ブロック暗号など) を実装するオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="c9d9b-108">たとえば、開発者がバイトセットの SHA1 ハッシュを計算するとします。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="c9d9b-109">名前<xref:System.Security.Cryptography>空間には、SHA1 アルゴリズムの2つの実装 (純粋に管理された実装と CryptoAPI をラップする実装) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="c9d9b-110">開発者は、 **new**演算子を呼び出すことによって、 <xref:System.Security.Cryptography.SHA1Managed>特定の SHA1 実装 (など) をインスタンス化することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="c9d9b-111">ただし、クラスで SHA1 ハッシュアルゴリズムが実装されている限り、共通言語ランタイムがどのクラスを読み込むかに関係なく、開発者は<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>メソッドを呼び出してオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c9d9b-112">このメソッドは、 **CreateFromName ("CryptoConfig")** を呼び出します。これは、SHA1 ハッシュアルゴリズムの実装を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="c9d9b-113">また、 **CryptoConfig**を呼び出すこともできます。これは、既定では、暗号化構成には .NET Framework に出荷されるアルゴリズムの短い名前が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="c9d9b-114">どのハッシュアルゴリズムが使用されているかに関係なく、開発者<xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>はメソッドを呼び出すことができます。このメソッドは、ハッシュ変換を実装するオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="c9d9b-115">構成ファイルでのアルゴリズム名のマッピング</span><span class="sxs-lookup"><span data-stu-id="c9d9b-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="c9d9b-116">既定では、ランタイムは 4 <xref:System.Security.Cryptography.SHA1CryptoServiceProvider>つのシナリオすべてに対してオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="c9d9b-117">ただし、コンピューターの管理者は、最後の2つのシナリオのメソッドが返すオブジェクトの種類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="c9d9b-118">これを行うには、わかりやすいアルゴリズム名をマシン構成ファイル (machine.config) で使用するクラスにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="c9d9b-119">次の例では、 **CryptoConfig、CreateFromName ("SHA1")** 、および HashAlgorithm を実行するようにランタイムを構成する方法を示しています。この例を次に示します。オブジェクトを`MySHA1HashClass`返します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="c9d9b-120">[< Cryptoclass\>要素](./file-schema/cryptography/cryptoclass-element.md)で属性の名前を指定できます (前の例では、属性`MySHA1Hash`に名前を指定します)。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-120">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="c9d9b-121">Cryptoclass > 要素の属性 **\<** の値は、共通言語ランタイムがクラスを検索するために使用する文字列です。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="c9d9b-122">[「完全修飾型名の指定](../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で指定した要件を満たす任意の文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="c9d9b-123">多くのアルゴリズム名は、同じクラスにマップできます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="c9d9b-124">[ \<Nameentry > 要素](./file-schema/cryptography/nameentry-element.md)は、クラスを1つのわかりやすいアルゴリズム名にマップします。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-124">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="c9d9b-125">**Name**属性には、 **CryptoConfig**メソッドを呼び出すときに使用される文字列、または<xref:System.Security.Cryptography>名前空間の抽象暗号化クラスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="c9d9b-126">**Class**属性の値は、  **\<cryptoclass >** 要素の属性の名前です。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9d9b-127">Sha1 アルゴリズムを取得するには、 <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>または**CryptoConfig CreateFromName ("SHA1")** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="c9d9b-128">各メソッドは、SHA1 アルゴリズムを実装するオブジェクトを返すことだけを保証します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="c9d9b-129">アルゴリズムの各フレンドリ名を、構成ファイル内の同じクラスにマップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="c9d9b-130">既定の名前とマップ先のクラスの一覧については<xref:System.Security.Cryptography.CryptoConfig>、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d9b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9d9b-131">See also</span></span>

- [<span data-ttu-id="c9d9b-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c9d9b-132">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c9d9b-133">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="c9d9b-133">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
