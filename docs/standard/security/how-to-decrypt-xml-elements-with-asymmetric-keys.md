---
title: '方法: 非対称キーで XML 要素を復号化する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 303c7db984b682d24a8f0e00160eb2d0827a84e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314426"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="1c4d9-102">方法: 非対称キーで XML 要素を復号化する</span><span class="sxs-lookup"><span data-stu-id="1c4d9-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="1c4d9-103"><xref:System.Security.Cryptography.Xml> 名前空間のクラスを使用して、XML ドキュメント内の要素を暗号化および復号化することができます。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="1c4d9-104">XML 暗号化は、データが簡単に読み取られる心配なく、暗号化された XML データを交換または保存する標準的な方法です。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="1c4d9-105">標準の XML 暗号化の詳細については、World Wide Web Consortium (W3C) の推奨事項を参照してください。 [XML 署名の構文と処理](https://www.w3.org/TR/xmldsig-core/)します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="1c4d9-106">この手順の例で説明する方法を使用して暗号化された XML 要素を復号化[方法。非対称キーで XML 要素を暗号化する](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="1c4d9-107">見つけた、<`EncryptedData`> 要素は、要素を復号化し、元のプレーン テキストの XML 要素を持つ要素を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="1c4d9-108">この例では、2 つのキーを使用して XML 要素を復号化します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="1c4d9-109">キー コンテナーから以前に生成された RSA 秘密キーを取得し、使用してセッション キーを復号化する RSA キーに格納されている、<`EncryptedKey`> の要素、<`EncryptedData`> 要素。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="1c4d9-110">例では、セッション キーを使用して XML 要素を復号化します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="1c4d9-111">この例は、複数のアプリケーションが暗号化されたデータを共有する必要がある状況や、1 つのアプリケーションが、実行する時間の間に暗号化されたデータを保存する必要がある状況に適しています。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="1c4d9-112">非対称キーで XML 要素を復号化するには</span><span class="sxs-lookup"><span data-stu-id="1c4d9-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="1c4d9-113"><xref:System.Security.Cryptography.CspParameters> オブジェクトを作成し、キーのコンテナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="1c4d9-114"><xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを使用して、コンテナーから以前に生成された非対称キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="1c4d9-115"><xref:System.Security.Cryptography.CspParameters> オブジェクトを <xref:System.Security.Cryptography.RSACryptoServiceProvider> コンストラクターに渡すと、キー コンテナーからキーが自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="1c4d9-116"><xref:System.Security.Cryptography.Xml.EncryptedXml> オブジェクトを新規作成してドキュメントを復号化します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="1c4d9-117">復号化が必要なドキュメント内で RSA キーと要素と関連付けるには、キーと名前のマッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="1c4d9-118">ドキュメントを暗号化したときに使用したキーと同じ名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="1c4d9-119">この名前は、手順 1 で指定されたキー コンテナー内のキーを識別するために使用する名前とは別であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="1c4d9-120">呼び出す、<xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>復号化するメソッド、<`EncryptedData`> 要素。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="1c4d9-121">このメソッドは、RSA キーを使用してセッション キーを復号化してから、自動的にセッション キーを使用して、XML 要素を復号化します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="1c4d9-122">自動的に置き換えられます、<`EncryptedData`> 元のプレーン テキストを持つ要素。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="1c4d9-123">XML ドキュメントを保存します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1c4d9-124">例</span><span class="sxs-lookup"><span data-stu-id="1c4d9-124">Example</span></span>  
 <span data-ttu-id="1c4d9-125">この例では、`test.xml` という名前のファイルがコンパイル済みのプログラムと同じディレクトリに存在することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="1c4d9-126">これも想定`test.xml`で説明する手法を使用して暗号化された XML 要素を含む[方法。非対称キーで XML 要素を暗号化する](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c4d9-127">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="1c4d9-127">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1c4d9-128">この例をコンパイルするには、`System.Security.dll` への参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="1c4d9-129">名前空間 <xref:System.Xml>、<xref:System.Security.Cryptography>、および <xref:System.Security.Cryptography.Xml> を含めます。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1c4d9-130">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1c4d9-130">.NET Framework Security</span></span>  
 <span data-ttu-id="1c4d9-131">対称暗号化キーをプレーンテキストで保存したり、対称キーをコンピューター間でプレーンテキストで転送したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="1c4d9-132">加えて、非対称キー ペアの秘密キーをプレーンテキストで保存または転送しないでください。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="1c4d9-133">対称暗号化キーと非対称暗号化キーの詳細については、[暗号化と復号化キーを生成する](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="1c4d9-134">キーをソース コードに直接埋め込まないでください。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="1c4d9-135">埋め込まれたキーが簡単に読み取れるアセンブリからを使用して[Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)またはメモ帳などのテキスト エディターでアセンブリを開くことで。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="1c4d9-136">暗号化キーを使用して完了したら、各バイトをゼロ (0) にするか、マネージド暗号化クラスの <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> メソッドを呼び出してメモリから消去します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="1c4d9-137">暗号化キーは、デバッガーによってメモリから読み取られるか、メモリの位置がディスクにページングされている場合はハード ドライブから読み取られることがあります。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4d9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c4d9-138">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="1c4d9-139">方法: 非対称キーで XML 要素を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="1c4d9-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
