---
title: Visual Basic での文字列の暗号化と復号化
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: ee8691fedb537d1aa588eaac61624b445da64d1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944424"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="d83aa-102">チュートリアル: Visual Basic での文字列の暗号化と復号化</span><span class="sxs-lookup"><span data-stu-id="d83aa-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="d83aa-103">このチュートリアルでは、 <xref:System.Security.Cryptography.DESCryptoServiceProvider>クラスを使用して、トリプルデータ暗号化標準 (<xref:System.Security.Cryptography.TripleDES>) アルゴリズムの暗号化サービスプロバイダー (CSP) バージョンを使用して文字列を暗号化および復号化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="d83aa-104">最初の手順では、3DES アルゴリズムをカプセル化し、暗号化されたデータを base-64 エンコード文字列として格納する単純なラッパークラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="d83aa-105">次に、このラッパーを使用して、プライベートユーザーデータをパブリックにアクセスできるテキストファイルに安全に格納します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="d83aa-106">暗号化を使用してユーザーシークレット (パスワードなど) を保護し、承認されていないユーザーが資格情報を読み取れないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d83aa-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="d83aa-107">これにより、承認されたユーザーの id を盗難から保護し、ユーザーの資産を保護し、否認不可を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d83aa-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="d83aa-108">また、暗号化を使用すると、承認されていないユーザーがユーザーのデータにアクセスするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d83aa-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="d83aa-109">詳細については、「[暗号サービス](../../../../standard/security/cryptographic-services.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d83aa-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d83aa-110">Rijndael (現時点では Advanced Encryption Standard [AES]) と Triple Data Encryption Standard (3DES) アルゴリズムは、計算に負荷がかかるため、DES よりも強力なセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="d83aa-111">詳細については、次のトピックを参照してください。 <xref:System.Security.Cryptography.DES> および <xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="d83aa-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="d83aa-112">暗号化ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="d83aa-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="d83aa-113">クラスを`Simple3Des`作成して、暗号化と復号化の方法をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="d83aa-114">暗号化名前空間のインポートを、 `Simple3Des`クラスを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="d83aa-115">`Simple3Des`クラスに、3des 暗号化サービスプロバイダーを格納するためのプライベートフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="d83aa-116">指定したキーのハッシュから、指定した長さのバイト配列を作成するプライベートメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="d83aa-117">3DES 暗号化サービスプロバイダーを初期化するコンストラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="d83aa-118">パラメーター `key`は、メソッド`EncryptData`および`DecryptData`メソッドを制御します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="d83aa-119">文字列を暗号化するパブリックメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="d83aa-120">文字列を復号化するパブリックメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="d83aa-121">これで、ラッパークラスを使用してユーザー資産を保護できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d83aa-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="d83aa-122">この例では、プライベートユーザーデータをパブリックにアクセスできるテキストファイルに安全に格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d83aa-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="d83aa-123">暗号化ラッパーをテストするには</span><span class="sxs-lookup"><span data-stu-id="d83aa-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="d83aa-124">別のクラスで、ラッパーの`EncryptData`メソッドを使用して文字列を暗号化し、それをユーザーの [マイドキュメント] フォルダーに書き込むメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="d83aa-125">暗号化された文字列をユーザーのマイドキュメントフォルダーから読み取り、その文字列をラッパーの`DecryptData`メソッドで復号化するメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="d83aa-126">メソッド`TestEncoding` と`TestDecoding`メソッドを呼び出すユーザーインターフェイスコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="d83aa-127">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d83aa-127">Run the application.</span></span>  
  
     <span data-ttu-id="d83aa-128">アプリケーションをテストするときに、間違ったパスワードを指定した場合、データの暗号化が解除されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d83aa-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83aa-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="d83aa-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="d83aa-130">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="d83aa-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
