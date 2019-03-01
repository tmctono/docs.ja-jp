---
title: Visual Basic における文字列の暗号化および暗号化
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: fe91e0062ac35859a3b85eb080d16fb88a6f9aaf
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972782"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="e29d7-102">チュートリアル: Visual Basic における文字列の暗号化および暗号化</span><span class="sxs-lookup"><span data-stu-id="e29d7-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="e29d7-103">このチュートリアルは、使用する方法を示します、<xref:System.Security.Cryptography.DESCryptoServiceProvider>暗号化し、Triple Data Encryption Standard の暗号化サービス プロバイダー (CSP) のバージョンを使用して文字列を復号化するクラス (<xref:System.Security.Cryptography.TripleDES>) アルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="e29d7-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="e29d7-104">最初の手順では、3 des アルゴリズムをカプセル化して、base 64 エンコード文字列として、暗号化されたデータを格納する単純なラッパー クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="e29d7-105">次に、そのラッパーを使用して、ユーザーの個人データをパブリックにアクセスできるテキスト ファイルを安全に格納します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="e29d7-106">ユーザー シークレット (パスワードなど) の保護を承認されていないユーザーの資格情報を解読できないようにするには、暗号化を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e29d7-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="e29d7-107">これは、ユーザーの資産を保護して、否認不可を提供する承認されたユーザーの id が盗まれないを保護できます。</span><span class="sxs-lookup"><span data-stu-id="e29d7-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="e29d7-108">また、暗号化は、承認されていないユーザーへのアクセスをユーザーのデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="e29d7-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="e29d7-109">詳細については、「[暗号サービス](../../../../standard/security/cryptographic-services.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e29d7-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e29d7-110">(Advanced Encryption Standard [AES] として参照されるようになりました) Rijndael と Triple Data Encryption Standard (3 des) アルゴリズム詳細いるため、DES よりも優れたセキュリティを提供負荷の大きい計算します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="e29d7-111">詳細については、次のトピックを参照してください。 <xref:System.Security.Cryptography.DES> および <xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="e29d7-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="e29d7-112">暗号化ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e29d7-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="e29d7-113">作成、`Simple3Des`暗号化と復号化メソッドをカプセル化するクラス。</span><span class="sxs-lookup"><span data-stu-id="e29d7-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2.  <span data-ttu-id="e29d7-114">含むファイルの先頭に、暗号化の名前空間のインポートを追加、`Simple3Des`クラス。</span><span class="sxs-lookup"><span data-stu-id="e29d7-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3.  <span data-ttu-id="e29d7-115">`Simple3Des`クラスに 3 des 暗号化サービス プロバイダーを格納するプライベート フィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4.  <span data-ttu-id="e29d7-116">指定したキーのハッシュから指定した長さのバイト配列を作成するプライベート メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5.  <span data-ttu-id="e29d7-117">3 des 暗号化サービス プロバイダーを初期化するコンス トラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="e29d7-118">`key`パラメーター コントロール、`EncryptData`と`DecryptData`メソッド。</span><span class="sxs-lookup"><span data-stu-id="e29d7-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6.  <span data-ttu-id="e29d7-119">文字列を暗号化するパブリック メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7.  <span data-ttu-id="e29d7-120">文字列を復号化するパブリック メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="e29d7-121">ラッパー クラスは、ユーザーの資産を保護するようになりました使用できます。</span><span class="sxs-lookup"><span data-stu-id="e29d7-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="e29d7-122">この例では、パブリックにアクセスできるテキスト ファイルにユーザーの個人データを安全に保管する使用されます。</span><span class="sxs-lookup"><span data-stu-id="e29d7-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="e29d7-123">暗号化のラッパーをテストするには</span><span class="sxs-lookup"><span data-stu-id="e29d7-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="e29d7-124">別のクラスのラッパーを使用するメソッドを追加`EncryptData`メソッドは文字列の暗号化をユーザーに書き込むことのマイ ドキュメント フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e29d7-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2.  <span data-ttu-id="e29d7-125">ユーザーから、暗号化された文字列を読み取るメソッドのマイ ドキュメント フォルダーと、ラッパーの文字列を復号化を追加`DecryptData`メソッド。</span><span class="sxs-lookup"><span data-stu-id="e29d7-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3.  <span data-ttu-id="e29d7-126">呼び出すユーザー インターフェイスのコードを追加、`TestEncoding`と`TestDecoding`メソッド。</span><span class="sxs-lookup"><span data-stu-id="e29d7-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="e29d7-127">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e29d7-127">Run the application.</span></span>  
  
     <span data-ttu-id="e29d7-128">アプリケーションをテストする場合は、こと、暗号化は解除されません、データ、間違ったパスワードを指定する場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e29d7-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29d7-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e29d7-129">See also</span></span>
- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="e29d7-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e29d7-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
