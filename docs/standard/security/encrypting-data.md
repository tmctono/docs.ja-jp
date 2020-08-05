---
title: データの暗号化
description: 対称アルゴリズムまたは非対称アルゴリズムを使用して、.NET でデータを暗号化する方法について説明します。
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 8a8b5988a13ab571284b08c7aaece3542467aa71
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556970"
---
# <a name="encrypting-data"></a><span data-ttu-id="11009-103">データの暗号化</span><span class="sxs-lookup"><span data-stu-id="11009-103">Encrypting Data</span></span>

<span data-ttu-id="11009-104">対称暗号化と非対称暗号化は、異なるプロセスを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="11009-104">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="11009-105">対称暗号化は、ストリーム上で実行されるため、大量のデータの暗号化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11009-105">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="11009-106">非対称暗号化は、少ないバイト数で実行されるため、少量のデータにのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11009-106">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="11009-107">対称暗号化</span><span class="sxs-lookup"><span data-stu-id="11009-107">Symmetric Encryption</span></span>  

<span data-ttu-id="11009-108">マネージド対称暗号化クラスは、ストリームに読み取られるデータを暗号化する <xref:System.Security.Cryptography.CryptoStream> という特別なストリーム クラスと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="11009-108">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="11009-109">**Cryptostream**クラスは、マネージストリームクラス、インターフェイスを実装するクラス <xref:System.Security.Cryptography.ICryptoTransform> (暗号アルゴリズムを実装するクラスから作成)、および <xref:System.Security.Cryptography.CryptoStreamMode> **cryptostream**に許可されているアクセスの種類を記述する列挙体を使用して初期化されます。</span><span class="sxs-lookup"><span data-stu-id="11009-109">The **CryptoStream** class is initialized with a managed stream class, a class that implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="11009-110">**CryptoStream**クラスは、クラスから派生した任意のクラス (、、など) を使用して初期化でき <xref:System.IO.Stream> <xref:System.IO.FileStream> <xref:System.IO.MemoryStream> <xref:System.Net.Sockets.NetworkStream> ます。</span><span class="sxs-lookup"><span data-stu-id="11009-110">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="11009-111">これらのクラスを使用すると、さまざまなストリーム オブジェクトの対称暗号化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="11009-111">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
<span data-ttu-id="11009-112">次の例は、アルゴリズムの既定の実装クラスの新しいインスタンスを作成する方法を示してい <xref:System.Security.Cryptography.Aes> ます。</span><span class="sxs-lookup"><span data-stu-id="11009-112">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="11009-113">インスタンスは、 **CryptoStream**クラスで暗号化を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="11009-113">The instance is used to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="11009-114">この例では、 **CryptoStream** は `myStream` と呼ばれるストリーム オブジェクトで初期化されています。これは任意の種類のマネージド ストリームにすることができます。</span><span class="sxs-lookup"><span data-stu-id="11009-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="11009-115">**Aes**クラスの**createencryptor**メソッドには、暗号化に使用されるキーと IV が渡されます。</span><span class="sxs-lookup"><span data-stu-id="11009-115">The **CreateEncryptor** method from the **Aes** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="11009-116">この場合、 `aes` から生成された既定のキーと IV が使用されます。</span><span class="sxs-lookup"><span data-stu-id="11009-116">In this case, the default key and IV generated from `aes` are used.</span></span>
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
<span data-ttu-id="11009-117">このコードを実行すると、 **CryptoStream**オブジェクトに書き込まれたデータは、AES アルゴリズムを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="11009-117">After this code is executed, any data written to the **CryptoStream** object is encrypted using the AES algorithm.</span></span>  
  
<span data-ttu-id="11009-118">次の例は、ストリームの作成、ストリームの暗号化、ストリームへの書き込み、およびストリームを閉じるプロセス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="11009-118">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="11009-119">この例では、 **CryptoStream**クラスと**Aes**クラスを使用して暗号化されたファイルストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="11009-119">This example creates a file stream that is encrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="11009-120"><xref:System.IO.StreamWriter> クラスを使用して、暗号化されたストリームにメッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="11009-120">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

<span data-ttu-id="11009-121">このコードは、AES 対称アルゴリズムを使用してストリームを暗号化し、"Hello World!" を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="11009-121">The code encrypts the stream using the AES symmetric algorithm, and writes "Hello World!"</span></span> <span data-ttu-id="11009-122">ストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="11009-122">to the stream.</span></span> <span data-ttu-id="11009-123">コードが正常に実行されると、 *TestData.txt*という名前の暗号化されたファイルが作成され、次のテキストがコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="11009-123">If the code is successful, it creates an encrypted file named *TestData.txt* and displays the following text to the console:</span></span>  
  
```console  
The text was encrypted.  
```  

<span data-ttu-id="11009-124">ファイルの暗号化を解除するには、[データ](decrypting-data.md)の暗号化解除の対称復号化の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="11009-124">You can decrypt the file by using the symmetric decryption example in [Decrypting Data](decrypting-data.md).</span></span> <span data-ttu-id="11009-125">この例とこの例では、同じキーと IV を指定しています。</span><span class="sxs-lookup"><span data-stu-id="11009-125">That example and this example specify the same key and IV.</span></span>

<span data-ttu-id="11009-126">ただし、例外が発生した場合、コードは次のテキストをコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="11009-126">However, if an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The encryption failed.  
```

## <a name="asymmetric-encryption"></a><span data-ttu-id="11009-127">非対称暗号化</span><span class="sxs-lookup"><span data-stu-id="11009-127">Asymmetric Encryption</span></span>

<span data-ttu-id="11009-128">非対称アルゴリズムは、通常は対称キーと IV の暗号化など、少量のデータの暗号化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="11009-128">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="11009-129">通常、非対称暗号化を行う個人や組織は、別のパーティによって生成された公開キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="11009-129">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="11009-130">クラスは、 <xref:System.Security.Cryptography.RSA> この目的のために .net によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="11009-130">The <xref:System.Security.Cryptography.RSA> class is provided by .NET for this purpose.</span></span>  
  
<span data-ttu-id="11009-131">次の例では、公開キーの情報を使用して対称キーと IV を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="11009-131">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="11009-132">サード パーティの公開キーを表す 2 つのバイト配列が初期化されます。</span><span class="sxs-lookup"><span data-stu-id="11009-132">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="11009-133"><xref:System.Security.Cryptography.RSAParameters> オブジェクトがこれらの値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="11009-133">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="11009-134">次に、 **RSAParameters**オブジェクト (それが表す公開キー) を、メソッドを使用して**RSA**インスタンスにインポートし <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="11009-134">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSA** instance using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="11009-135">最後に、クラスによって作成された秘密キーと IV <xref:System.Security.Cryptography.Aes> が暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="11009-135">Finally, the private key and IV created by an <xref:System.Security.Cryptography.Aes> class are encrypted.</span></span> <span data-ttu-id="11009-136">この例では、システムに 128 ビット暗号化がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11009-136">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
    End Sub

End Module
```  
  
```csharp  
using System;
using System.Security.Cryptography;

class Class1
{
    static void Main()
    {
        //Initialize the byte arrays to the public key information.  
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="11009-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="11009-137">See also</span></span>

- [<span data-ttu-id="11009-138">暗号化と復号化のためのキーの生成</span><span class="sxs-lookup"><span data-stu-id="11009-138">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="11009-139">データの復号化</span><span class="sxs-lookup"><span data-stu-id="11009-139">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="11009-140">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="11009-140">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="11009-141">クロスプラットフォーム暗号化</span><span class="sxs-lookup"><span data-stu-id="11009-141">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="11009-142">パディングを使用した CBC モードの対称復号化に関するタイミングの脆弱性</span><span class="sxs-lookup"><span data-stu-id="11009-142">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="11009-143">データ保護の ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="11009-143">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
