---
title: 文字列の暗号化と複合化
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 36e405c7362993471d3e6da8e319bccb854e1026
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343584"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="edebd-102">チュートリアル: Visual Basic での文字列の暗号化と暗号化解除</span><span class="sxs-lookup"><span data-stu-id="edebd-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="edebd-103">このチュートリアルでは、<xref:System.Security.Cryptography.DESCryptoServiceProvider> クラスを使用して、Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) アルゴリズムの暗号化サービス プロバイダー (CSP) バージョンを使用して文字列を暗号化および復号化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edebd-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="edebd-104">最初の手順は、3DES アルゴリズムをカプセル化し、暗号化されたデータを base-64 エンコード文字列として格納する単純なラッパー クラスを作成することです。</span><span class="sxs-lookup"><span data-stu-id="edebd-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="edebd-105">次に、そのラッパーを使用して、プライベート ユーザー データをパブリックにアクセス可能なテキスト ファイルに安全に格納します。</span><span class="sxs-lookup"><span data-stu-id="edebd-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="edebd-106">暗号化を使用すると、ユーザー シークレット (パスワードなど) を保護し、承認されていないユーザーが資格情報を読み取れないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="edebd-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="edebd-107">これにより、承認されたユーザーの ID を盗難から保護し、ユーザーの資産を保護し、否認防止を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="edebd-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="edebd-108">暗号化を使用すると、承認されていないユーザーによるアクセスからユーザーのデータを保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="edebd-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="edebd-109">詳細については、「[暗号サービス](../../../../standard/security/cryptographic-services.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="edebd-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="edebd-110">Rijndael (現在は Advanced Encryption Standard [AES] と呼ばれています) アルゴリズムと Triple Data Encryption Standard (3DES) アルゴリズムは、計算量が多いため、DES よりも優れたセキュリティを実現できます。</span><span class="sxs-lookup"><span data-stu-id="edebd-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="edebd-111">詳細については、次のトピックを参照してください。 <xref:System.Security.Cryptography.DES> および <xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="edebd-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="edebd-112">暗号化ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="edebd-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="edebd-113">`Simple3Des` クラスを作成して、暗号化方法と復号化方法をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="edebd-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="edebd-114">暗号化名前空間のインポートを `Simple3Des` クラスを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="edebd-115">`Simple3Des` クラスで、3DES 暗号化サービス プロバイダーを格納するプライベート フィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="edebd-116">指定されたキーのハッシュから指定された長さのバイト配列を作成するプライベート メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="edebd-117">3DES 暗号化サービス プロバイダーを初期化するコンストラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="edebd-118">`key`パラメーターを使用して、`EncryptData` メソッドと `DecryptData` メソッドを制御します。</span><span class="sxs-lookup"><span data-stu-id="edebd-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="edebd-119">文字列を暗号化するパブリック メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="edebd-120">文字列を復号化するパブリック メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="edebd-121">これで、ラッパー クラスを使用してユーザー資産を保護できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="edebd-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="edebd-122">この例では、パブリックにアクセスできるテキスト ファイルにプライベート ユーザー データを安全に格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edebd-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="edebd-123">暗号化ラッパーをテストするには</span><span class="sxs-lookup"><span data-stu-id="edebd-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="edebd-124">別のクラスで、ラッパーの `EncryptData` メソッドを使用して文字列を暗号化し、それをユーザーのマイ ドキュメント フォルダーに書き込むメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="edebd-125">ユーザーのマイ ドキュメント フォルダーから暗号化された文字列を読み取り、ラッパーの `DecryptData` メソッドを使用して文字列を復号化するメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="edebd-126">`TestEncoding` メソッドと `TestDecoding` メソッドを呼び出すユーザー インターフェイス コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="edebd-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="edebd-127">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="edebd-127">Run the application.</span></span>  
  
     <span data-ttu-id="edebd-128">アプリケーションをテストするときに間違ったパスワードを指定した場合、データが復号化されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="edebd-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edebd-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="edebd-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="edebd-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="edebd-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
