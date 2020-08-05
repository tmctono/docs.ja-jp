---
title: データの復号化
description: 対称アルゴリズムまたは非対称アルゴリズムを使用して、.NET でデータを復号化する方法について説明します。
ms.date: 07/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 2ba4c3ba43d688aeb66c67ec3f94f4a503d47892
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556983"
---
# <a name="decrypting-data"></a><span data-ttu-id="658e0-103">データの復号化</span><span class="sxs-lookup"><span data-stu-id="658e0-103">Decrypting Data</span></span>

<span data-ttu-id="658e0-104">復号化は、暗号化の逆の操作です。</span><span class="sxs-lookup"><span data-stu-id="658e0-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="658e0-105">秘密キーの暗号化では、データの暗号化に使用されたキーと IV の両方を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="658e0-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="658e0-106">公開キーの暗号化では、公開キー (データが秘密キーで暗号化された場合) または秘密キー (データが公開キーで暗号化された場合) のいずれかを把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="658e0-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="658e0-107">対称復号化</span><span class="sxs-lookup"><span data-stu-id="658e0-107">Symmetric Decryption</span></span>

<span data-ttu-id="658e0-108">対称アルゴリズムで暗号化されたデータの復号化は、対称アルゴリズムでデータを暗号化する際に使用するプロセスと似ています。</span><span class="sxs-lookup"><span data-stu-id="658e0-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="658e0-109">クラスは、 <xref:System.Security.Cryptography.CryptoStream> 任意のマネージストリームオブジェクトから読み取られたデータの暗号化を解除するために .net によって提供される対称暗号化クラスと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="658e0-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="658e0-110">次の例は、アルゴリズムの既定の実装クラスの新しいインスタンスを作成する方法を示してい <xref:System.Security.Cryptography.Aes> ます。</span><span class="sxs-lookup"><span data-stu-id="658e0-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="658e0-111">インスタンスは、オブジェクトの復号化を実行するために使用され <xref:System.Security.Cryptography.CryptoStream> ます。</span><span class="sxs-lookup"><span data-stu-id="658e0-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="658e0-112">この例では、最初に**Aes**実装クラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="658e0-112">This example first creates a new instance of the **Aes** implementation class.</span></span> <span data-ttu-id="658e0-113">次に、 **CryptoStream** オブジェクトを作成して、 `myStream`というマネージド ストリームの値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="658e0-113">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="658e0-114">次に、 **Aes**クラスの**createdecryptor**化メソッドに、暗号化に使用されたキーと IV が渡され、 **CryptoStream**コンストラクターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="658e0-114">Next, the **CreateDecryptor** method from the **Aes** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="658e0-115">次の例は、ストリームの作成、ストリームの復号化、ストリームからの読み取り、およびストリームを閉じるプロセス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="658e0-115">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="658e0-116">*TestData.txt*という名前のファイルを読み取るファイルストリームオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="658e0-116">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="658e0-117">ファイルストリームは、 **CryptoStream**クラスと**Aes**クラスを使用して復号化されます。</span><span class="sxs-lookup"><span data-stu-id="658e0-117">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="658e0-118">この例では、[データの暗号化](encrypting-data.md)に対称暗号化の例で使用されるキーと IV の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="658e0-118">This example specifies key and IV values that are used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="658e0-119">これらの値の暗号化および転送に必要なコードは示されていません。</span><span class="sxs-lookup"><span data-stu-id="658e0-119">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Security.Cryptography

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Create a file stream.
            Dim myStream As FileStream = new FileStream("TestData.txt", FileMode.Open)

            'Create a new instance of the default Aes implementation class
            'and decrypt the stream.
            Dim aes As Aes = Aes.Create()

            'Create an instance of the CryptoStream class, pass it the file stream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            myStream.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The decryption Failed.")
            Throw
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

class Class1
{
    static void Main(string[] args)
    {
        //The key and IV must be the same values that were used
        //to encrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        byte[] iv = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        try
        {
            //Create a file stream.
            FileStream myStream = new FileStream("TestData.txt", FileMode.Open);

            //Create a new instance of the default Aes implementation class
            Aes aes = Aes.Create();

            //Create a CryptoStream, pass it the file stream, and decrypt
            //it with the Aes class using the key and IV.
            CryptoStream cryptStream = new CryptoStream(
               myStream,
               aes.CreateDecryptor(key, iv),
               CryptoStreamMode.Read);

            //Read the stream.
            StreamReader sReader = new StreamReader(cryptStream);

            //Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

            //Close the streams.
            sReader.Close();
            myStream.Close();
        }
        //Catch any exceptions.
        catch
        {
            Console.WriteLine("The decryption failed.");
            throw;
        }
    }
}
```

<span data-ttu-id="658e0-120">前の例では、対称暗号化の例で使用したのと同じキー、IV、およびアルゴリズムを使用して[データを暗号化](encrypting-data.md)しています。</span><span class="sxs-lookup"><span data-stu-id="658e0-120">The preceding example uses the same key, IV, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="658e0-121">この例で作成された*TestData.txt*ファイルの暗号化を解除し、元のテキストをコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="658e0-121">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="658e0-122">非対称復号化</span><span class="sxs-lookup"><span data-stu-id="658e0-122">Asymmetric Decryption</span></span>

<span data-ttu-id="658e0-123">通常は、パーティ (パーティ A) は、公開キーと秘密キーの両方を生成し、メモリ内、または暗号化キー コンテナーのいずれかに格納します。</span><span class="sxs-lookup"><span data-stu-id="658e0-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="658e0-124">パーティ A は公開キーを別のパーティ (パーティ B) に送信します。</span><span class="sxs-lookup"><span data-stu-id="658e0-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="658e0-125">パーティ B は、公開キーを使用してデータを暗号化し、データをパーティ A に送り返します。パーティ A は、データを受信した後、対応する秘密キーを使用して復号化します。</span><span class="sxs-lookup"><span data-stu-id="658e0-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="658e0-126">復号化は、パーティ B がデータの暗号化に使用した公開キーに対応する秘密キーをパーティ A が使用する場合にのみ成功します。</span><span class="sxs-lookup"><span data-stu-id="658e0-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="658e0-127">セキュリティで保護された暗号化キー コンテナーに非対称キーを格納する方法と、その後非対称キーを取得する方法については、「 [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="658e0-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="658e0-128">次の例は、対称キーと IV を表す 2 つのバイト配列の復号化を示しています。</span><span class="sxs-lookup"><span data-stu-id="658e0-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="658e0-129">第三者に簡単に送信できる形式で <xref:System.Security.Cryptography.RSA> オブジェクトから非対称の公開キーを抽出する方法については、「 [Encrypting Data](encrypting-data.md)というマネージ ストリームの値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="658e0-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a><span data-ttu-id="658e0-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="658e0-130">See also</span></span>

- [<span data-ttu-id="658e0-131">暗号化と復号化のためのキーの生成</span><span class="sxs-lookup"><span data-stu-id="658e0-131">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="658e0-132">データの暗号化</span><span class="sxs-lookup"><span data-stu-id="658e0-132">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="658e0-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="658e0-133">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="658e0-134">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="658e0-134">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="658e0-135">クロスプラットフォーム暗号化</span><span class="sxs-lookup"><span data-stu-id="658e0-135">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="658e0-136">パディングを使用した CBC モードの対称復号化に関するタイミングの脆弱性</span><span class="sxs-lookup"><span data-stu-id="658e0-136">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="658e0-137">データ保護の ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="658e0-137">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
